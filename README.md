# fast-forwardとnon-fast-forwardの違いと、それらを親ブランチにmergeした時のコミットログの違い。

## fast-forwardな関係
親ブランチ：master
コミットログ：A

子ブランチ：check-fast-forward
コミットログ：A => B

## fast-forwardな関係でmergeした場合のコミットログはどうなるか？
A. コミットログ：A => B  

## fast-forwardでない関係
親ブランチ：master
コミットログ：A => B => C

子ブランチ：non-fast-forward  
コミットログ：A => B => D


## fast-forwardでない関係で、mergeした場合のコミットログはどうなるか？  
A. コミットログ：A => B => C => D => **E**
2つのブランチがfast-forwardでない関係でmergeをすると、マージ後にコミット(E)が作成される。(コンフリクトがある場合は、修正してadd,commit）。
