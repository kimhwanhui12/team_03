# Changing the past

## 1. Rebasing
세 갈래(baguette, coffee, donut)로 나뉜 커밋을 rebase로 한 줄로 이은 뒤, main을 그 끝으로 옮긴다.
```bash
git checkout coffee
git rebase baguette
git checkout donut
git rebase coffee
git checkout main
git reset --hard donut
```

## 2. Reordering events
순서가 꼬인 커밋을 underwear → pants → shoes 순서로 다시 쌓는다. main을 첫 커밋으로 되돌린 뒤 cherry-pick으로 하나씩 가져온다.
```bash
git branch old
git reset --hard old~4
git cherry-pick old~1
git cherry-pick old~2
git cherry-pick old~3
git cherry-pick old
```