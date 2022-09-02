### Contributing

Developers must follow the [git-flow branching model](https://nvie.com/posts/a-successful-git-branching-model/) when contributing to this project and versioning must adhere to [Semantic Versioning](http://semver.org/).

#### Features

Use the following commands to start a feature:

```
git checkout main
git pull origin main
git checkout -b feature/feature_name
```

Once you start pushing commits, open a PR with your branch. The title for your PR should be:

```
feature: feature_name
```

When you are ready, request review for your feature PR on Github's UI, and approval + conversation resolution is required before the branch can be merged.

Make sure to update the changelog before you try to merge.

Once approved, merge your branch main in GitHub's UI, being sure to squash commits.  If you need to resolve conflicts, do the following:

```
git checkout main
git pull origin main
git checkout feature/feature_name
git merge --no-ff main
```

Now you resolve the conflicts locally. And then commit the changes with:

```
git add .
git commit -m "merge main into feature branch"
git push origin feature/feature_name
```

Now you should be good to Squash and Merge in GitHub's UI.

Next tag the release, using the appropriate [Semantic Version](http://semver.org/):

```
git checkout main
git pull origin main
git tag -a x.y.0
git push origin --tags
```

#### Hotfixes

Start a hotfix with the following commands:

```
git checkout main
git pull origin main
git checkout -b hotfix/hotfix_name
```

Create a PR for your hotfix with the title:

```
hotfix: hotfix_name
```

Make sure to update the changelog with the patch version.  Request review when ready to merge.

Once approved, merge the hotfix into main using GitHub's UI. If you have conflicts, resolving them using the same process as defined for features.

After merging, tag the hotfix with the new patch version:

```
git checkout main
git pull origin main
git tag -a x.y.z
git push origin --tags
```
