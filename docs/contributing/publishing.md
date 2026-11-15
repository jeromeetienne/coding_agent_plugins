# Publish and maintain the documentation

- Created: 9 November 2026
- Last updated: 15 November 2026
- Status: Maintained publication guide
- Related framing: [Documentation conventions](maintaining_skills.md)
- Related rules: [Docs folder system](../../skills/docs_folder_system/SKILL.md)
- Related issue: [Issue 53](https://github.com/jeromeetienne/coding_agent_plugin/issues/53), part of [Issue 37](https://github.com/jeromeetienne/coding_agent_plugin/issues/37)

## Publish a repository release

A Git tag identifies an exact version of the shared skills. A GitHub release presents the release notes for that tag. An installable package or additional download attachment is not required. Publishing a release does not update skills already installed in another project.

1. Prepare the version entry in [CHANGELOG.md](../../CHANGELOG.md), following [Keep a Changelog Workflow](../../skills/keep-a-changelog-workflow/SKILL.md). Verify that the changes belong to the selected version; keep later changes under Unreleased.
2. For a historical release, verify that the existing version tag identifies the expected repository state. Never move an existing tag or reconstruct a historical version from today's code. For a new version, merge the reviewed changes, then create and push the agreed version tag at the reviewed revision before publishing.
3. Copy the matching changelog entry into a temporary Markdown file, starting at `### Release notes` and including all categorized changes and source links. Exclude other versions, Unreleased, and the changelog's link definitions. Create a draft release using the exact existing tag and review the description.
4. Publish historical releases from oldest to newest, using `--latest=false` for older versions. Explicitly mark the newest completed version as latest. For the existing versions `0.1.0` through `0.5.0`, the latest is `0.5.0`. GitHub records publication when the release is published; the changelog retains its recorded historical dates.
5. Read each release back from GitHub. Confirm the tag, release notes, source links, published state, and latest-release designation. Reconcile the matching GitHub release if the maintained changelog notes need correction.

For example, after copying the `0.5.0` entry into `/tmp/0.5.0-release-notes.md`, create the draft:

```bash
gh release create 0.5.0 --repo jeromeetienne/coding_agent_plugins --verify-tag --draft --title '0.5.0' --notes-file /tmp/0.5.0-release-notes.md
```

After review, publish the newest completed version and verify the result:

```bash
gh release edit 0.5.0 --repo jeromeetienne/coding_agent_plugins --draft=false --latest
gh release view 0.5.0 --repo jeromeetienne/coding_agent_plugins --json tagName,name,body,isDraft,isPrerelease,url
gh api repos/jeromeetienne/coding_agent_plugins/releases/latest --jq '.tag_name'
```

## Read the published documentation

The public website is [Coding agent skills](https://jeromeetienne.github.io/coding_agent_plugin/). The website uses the same maintained Markdown as GitHub: the repository overview is the home page, individual skill README files are the skill introductions, and the shared guides remain in docs. There is no second copy of the content to synchronize.

## Publication configuration

In the repository settings, under Pages, the publication source is **Deploy from a branch**, with branch **main** and folder **/ (root)**. GitHub Pages publishes the repository through its built-in Jekyll renderer, which converts Markdown into website pages. The [site configuration](https://github.com/jeromeetienne/coding_agent_plugin/blob/main/_config.yml) selects the Cayman theme, site title, domain and repository path. See [GitHub's Jekyll documentation](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll) for the supported configuration.

The configured plugins render Markdown without adding a separate metadata block to each source file, use README files as directory introductions where no index exists, and convert relative Markdown links to published page addresses. The documentation folders already have index.md files for agents and tools. Their human overviews therefore remain separate pages at docs/README.html and docs/about_symbio_spec/README.html. All documentation README source paths are explicitly included in the configuration so the renderer processes those overviews too; see the [optional front matter plugin documentation](https://github.com/benbalter/jekyll-optional-front-matter#one-potential-gotcha).

The site includes the .agents directory so links to the repository rules configuration remain usable. Installed skill copies in .agents/skills, temporary worktrees in .agents/worktrees, and the .claude directory are excluded. Skill links use the authoritative source in skills/. Publication does not install or update a skill in a receiving project.

## Update content

1. Change the authoritative skill instructions only when a skill behaviour change is authorized. Update the affected skill README and shared guides in the same change so examples, required inputs and approval boundaries agree with the instructions.
2. Follow the [documentation conventions](maintaining_skills.md#documentation-conventions), update affected metadata dates and folder indexes, and check relative links. Maintain the [dependency reference](../using_skills/skills_together.md) when skills, readiness, dependencies or coverage change.
3. Review the Markdown changes and merge the pull request into main. GitHub Pages builds and publishes the updated website automatically from that branch.
4. Check the build status and the public pages affected by the change. A merge is not proof that publication succeeded.

## Check publication

For maintainers with authenticated GitHub access, inspect the publication source and latest build:

```bash
gh api repos/jeromeetienne/coding_agent_plugin/pages --jq '{build_type, source, html_url}'
gh api repos/jeromeetienne/coding_agent_plugin/pages/builds/latest --jq '{status, error, commit, updated_at}'
```

Confirm the configured source is main at the repository root and the latest build reports built. Compare the build's commit field with the expected source revision; the latest main revision can be read with:

```bash
gh api repos/jeromeetienne/coding_agent_plugin/commits/main --jq '.sha'
```

If a build is pending, wait for the build to finish before checking the updated pages. If a build reports an error, inspect the error and correct the source before claiming the website is updated.

Open the following public pages in a browser without signing in:

| Page | Public address |
| --- | --- |
| Home and complete skill list | [Home](https://jeromeetienne.github.io/coding_agent_plugin/) |
| Documentation overview | [Documentation](https://jeromeetienne.github.io/coding_agent_plugin/docs/README.html) |
| Individual skill introduction | [The Rules of the Repo](https://jeromeetienne.github.io/coding_agent_plugin/skills/rules_of_the_repo/) |
| Shared workflow guide | [Skills working together](https://jeromeetienne.github.io/coding_agent_plugin/docs/using_skills/skills_together.html) |
| Nested documentation overview | [About Symbiospec](https://jeromeetienne.github.io/coding_agent_plugin/docs/about_symbio_spec/README.html) |
| Nested documentation page | [What is Symbiospec](https://jeromeetienne.github.io/coding_agent_plugin/docs/about_symbio_spec/what_is_symbio_spec.html) |
| Repository rules configuration | [Rules list](https://jeromeetienne.github.io/coding_agent_plugin/.agents/rules_of_the_repo/rules_list.html) |

Follow the navigation from the home page to the documentation overview, skill introduction, shared workflow guide and nested Symbiospec pages. Load each changed page directly, test the relative links, and check that the theme's styles load. Confirm both documentation overview pages display formatted text rather than raw Markdown. Review the same pages in a narrow browser window, including long tables and code examples.

For example, this request without authentication checks that the shared workflow guide is served and prints the response content type:

```bash
curl --fail --location --write-out '\nResponse: %{http_code}; content type: %{content_type}\n' https://jeromeetienne.github.io/coding_agent_plugin/docs/using_skills/skills_together.html
```

A successful response establishes access to that page only. Inspect the returned content to establish which content is served. Source checks and HTTP requests cannot establish visual correctness. Report content review, build status, published page checks and visual review separately. If browser access is unavailable, report visual review as unperformed.

## Change the publication destination

Keep content in its existing authoritative locations. Agree on a new destination and publication process before changing hosting. Update the site configuration, repository links and this guide, and repeat the published-page and navigation checks. Keep receiving-project configuration and generated project documentation in the receiving project.
