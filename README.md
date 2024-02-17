<!-- markdownlint-disable MD033 MD041 -->
<h1 align="center">
    collection-of-update-action
</h1>

<p align="center">
    <strong>GitHub Action for automatic scheduled collection-of list updates.</strong>
</p>

<p align="center">
    <a href="https://collection-of.org" title="Collection-of Badge"><img src="http://bit.ly/3o3EHNN"></a>
    <a href="https://github.com/search?q=collection-of-lists+collection-of-update-action+path%3A.github%2Fworkflows+language%3AYAML+fork%3Atrue&type=code" title="Action Usage Count"><img src="https://img.shields.io/endpoint?url=https%3A%2F%2Fapi-git-master.endbug.vercel.app%2Fapi%2Fgithub-actions%2Fused-by%3Faction%3Dcollection-of-lists%2Fcollection-of-update-action%26badge%3Dtrue"></a>
    <a href="https://github.com/khulnasoft/collection-of-update-action/actions?query=workflow%3Abuild-pipeline" title="Build Status"><img src="https://img.shields.io/github/workflow/status/collection-of-lists/collection-of-update-action/build-pipeline"></a>
    <a href="https://gitter.im/khulnasoft/collection-of" title="Chat on Gitter"><img src="https://badges.gitter.im/khulnasoft/collection-of.svg"></a>
    <a href="https://collectionoflists.substack.com/subscribe" title="Subscribe for updates"><img src="http://bit.ly/2Md9rxM"></a>
    <a href="https://twitter.com/collection_of_lists" title="Collection-of on Twitter"><img src="https://img.shields.io/twitter/follow/collection_of_lists.svg?style=social&label=Follow"></a>
</p>

<p align="center">
  <a href="#getting-started">Getting Started</a> •
  <a href="#support--feedback">Support</a> •
  <a href="https://github.com/khulnasoft/collection-of-generator/issues/new?labels=bug&template=01_bug-report.md">Report a Bug</a> •
  <a href="#faq">FAQ</a> •
  <a href="#contribution">Contribution</a> •
  <a href="https://github.com/khulnasoft/collection-of-update-action/releases">Changelog</a>
</p>

The collection-of update action is a Github Action for automated and scheduled updates of collection-of markdown pages. It uses the [collection-of-generator](https://github.com/khulnasoft/collection-of-generator) CLI tool to generate and update a collection-of markdown page from a list of projects configured in a `yaml` file. We also provide a full workflow definition which automatically creates pull requests and Github releases for every update.

## Getting Started

> 🧙‍♂️ If you want to create your own collection-of list, we strongly recommend to follow [this guide](https://github.com/khulnasoft/collection-of/blob/main/create-collection-of-list.md). With the guide, it will only take about 3 minutes to get you started. It already includes this Github Action and some other useful template files. Further manual steps for setting up the Github Action are not required.

If you create a collection-of list using the [offical guide and template](#TODO), the full workflow is already included without any further requirements from your side. If you want to manually set-up this Github Action (without the template), we recommend to use the [`update-collection-of-list.yml` workflow](https://github.com/khulnasoft/collection-of-update-action/blob/main/workflows/update-collection-of-list.yml). It runs the collection-of generator, auto-commits all changes into a separated branch, auto-creates a pull request as well as a draft release for the update. For integration into an existing workflow, please refer to [this section](#integrate-into-existing-workflow). You can find documentation on the `projects.yaml` file and the markdown generation process in the [collection-of-generator documentation](https://github.com/khulnasoft/collection-of-generator#documentation).

#### Using the full workflow

To use the `update-collection-of-list` workflow, just copy [this file](https://github.com/khulnasoft/collection-of-update-action/blob/main/workflows/update-collection-of-list.yml) into the `.github/workflows/` folder of your repository. Once it is pushed into your repository, it will automatically run every seven days. You can also manually run this workflow by selecting: `Actions` -> `update-collection-of-list` -> `Run workflow` _(a version as input is not required)_.

#### Integrate into existing workflow

In case you only want to use the collection-of generator action itself to integrate it into an existing workflow, you can also just use the `collection-of-update-action` as a step in your workflow, for example:

```yaml
steps:
  - name: update-collection-of-list
    uses: khulnasoft/collection-of-update-action@v0.8.5
    with:
      github_key: ${{ secrets.GITHUB_TOKEN }}
      libraries_key: ${{ secrets.LIBRARIES_KEY }}
      projects_file: "./projects.yaml"
```

If you want to enable the collection-of generator to also fetch information from [libraries.io](https://libraries.io), make sure to add your libraries API key as a secret to the repository with the name `LIBRARIES_KEY`.

## Support & Feedback

You can find all channels for support, questions, and feedback in the [collection-of-generator documentation](https://github.com/khulnasoft/collection-of-generator#support--feedback). If you have found a bug or want to request a feature, please open an issue in the [collection-of-generator repository](https://github.com/khulnasoft/collection-of-generator/issues/new/choose) since issues are deactivated in this repository.

## Contribution

Contributions are very welcome. You can find information on how to contribute to this project in the [collection-of-generator repository](https://github.com/khulnasoft/collection-of-generator#contribution).

## Development

Refer to our [contribution guides](https://github.com/khulnasoft/collection-of-update-action/blob/main/CONTRIBUTING.md#development-instructions) for detailed information on our build scripts and development process.

---

Licensed **MIT**. Created and maintained with ❤️&nbsp; by developers from Berlin.
