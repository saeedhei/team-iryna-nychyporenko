git remote get-url origin

git remote remove origin
git remote add origin https://github.com/saeedhei/team-iryna-nychyporenko

python -m git_filter_repo --force --commit-callback '
if commit.author_email == b"xxx@gmail.com":
commit.skip()
'

git log --pretty=format:"Author: %an <%ae> | Committer: %cn <%ce>"
git log --all --pretty=format:"%an <%ae>" | sort | uniq
