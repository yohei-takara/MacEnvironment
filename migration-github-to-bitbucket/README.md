# リポジトリのimport

※ githubへはhttpsでのアクセスなので、2段階認証している場合は、アクセストークンを利用する

`https://bitbucket.org/repo/import`

古いリポジトリ に、GitHub リポジトリ リンク 
新規リポジトリ bitbucketに作成されるリポジトリ

# wikiのimport

1. github wikiを clone
1. `git remote -v`
1. `git remote rm origin`
1. `git remote add origin git@bitbucket.org:<team name>/<repo name>/wiki
1. `git remote -v`
1. `git push -f origin master`

