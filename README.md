# fast-forwardとnon-fast-forwardの違いと、それらを親ブランチにmergeした時のコミットログ。

## fast-forwardな関係
親ブランチ：master  
コミットログ：A

子ブランチ：check-fast-forward
コミットログ：A => B

## fast-forwardの関係でmergeした場合のコミットログを見る。
親ブランチ：master  
コミットログ：A

子ブランチ：check-fast-forward  
コミットログ：A => B

### Q. 上記の条件で、masterにcheck-fast-forwordをmergeすると、コミットログはどうなるか？  
#### A. コミットログ：A => B  

## fast-forwardでない関係で、mergeした場合のコミットログを見る。
親ブランチ：master
コミットログ：A => B => C

子ブランチ：non-fast-forward  
コミットログ：A => B => D

### Q. 上記の条件で、masterにcheck-non-fast-forwordをmergeすると、コミットログはどうなるか？  
#### A. コミットログ：A => B => C => D => **E**(fast-forwardでない関係のため、自動的に作成されたコミット。)
二つのブランチがfast-forwardでない関係の場合、マージ後にコミット(ここでは、E)が作成される。(コンフリクトがある場合は、修正してadd,commit)

コミットごとに追記。
- コミットB
- コミットC
- コミットD
- コミットE