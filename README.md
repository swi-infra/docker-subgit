Subgit Docker Image
===================

What is subgit ?
----------------

SubGit is a tool for a smooth, stress-free SVN to Git migration.
Create writable Git mirror of a local or remote Subversion repository and use both Subversion and Git as long as you like.
You may also do a fast one-time import from Subversion to Git or use SubGit within Atlassian Stash.

SubGit is a software from http://www.subgit.com/.
This image is simple way to deploy a subgit service to migrate.

How ?
-----

Image: [quay.io/swi-infra/subgit](https://quay.io/swi-infra/subgit/)

You need to expose your existing Git folder as the volume /repo.git.

This will start the translation using configuration stored in the `myrepo.git/subgit` folder:
```
docker run --name "subgit-myrepo" --volume /local/folder/myrepo.git:/repo.git quay.io/swi-infra/subgit
```

You can use the 'post-update' Git hook to eventually upload changes.

This image does not take care of assisting the subgit configuration process for a repository.
You can eventually execute directly the image to do subgit commands directly.
