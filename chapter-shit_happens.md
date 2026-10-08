# Shit happens

## 1. Restore a deleted file
실수로 지운 essay 파일을 마지막 커밋 상태로 되살린다.
```bash
git checkout essay
```

## 2. Restore a file from the past
첫 커밋의 essay(good version)를 꺼내 와서 새 커밋으로 남긴다.
```bash
git checkout HEAD~1 essay
git commit -m "Restore good version"
```

## 3. Undo a bad commit
오타 난 커밋을 reset으로 취소하고, 숫자를 고쳐서 다시 커밋한다.
```bash
git reset HEAD~1
echo "1 2 3 4 5 6 7 8 9 10" > numbers
git commit -am "More numbers"
```

## 4. I pushed something broken
이미 push한 커밋은 기록을 지우지 않고, 그 커밋을 되돌리는 새 커밋을 revert로 만들어 push한다.
```bash
git revert --no-edit HEAD~1
git push
```

## 5. Go back to where you were before
reflog로 HEAD가 지나온 위치를 확인하고(main으로 오기 전에 3에 있었음), 그곳으로 돌아간다.
```bash
git reflog
git checkout 3
```