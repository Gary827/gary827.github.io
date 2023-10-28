
# 20231025-LFS (Large File Storage)大型檔案儲存
* GIT的LFS，是大型檔案儲存(Large File Storage)，因為GitHub跟GitLab基本上無法預設支援單一檔案超過500MB，所以若要上船單一檔案超過500MB的話，需要使用LFS的機制協助上傳。
* 那這個LFS的作法就是它不會直接將檔案上傳到Repository，而是將檔案存放在其他地方，而我們在GitHub或GitLab上看到的檔案部分會顯示LFS，但是其代表的意思是指向到某個存放大型檔案的位置。不過使用LFS的話也是有單一檔案大小的限制，目前來說是5GB，因此，使用上還是要稍微注意一下這點。

## LFS在Repository之畫面
如果使用LFS，在檔案的後面就會有一個LFS的標籤
![](https://hackmd.io/_uploads/rJoufj4za.png)

## LFS用法
如果我們要針對某些檔案用LFS的方式儲存到遠端到儲存庫的話，要使用以下步驟
先安裝LFS
```
git install lfs
```
設定要LFS追蹤的檔案，這部分可以使用*表示全部
```
git lfs track <path-to-file>
```

如果單純下以下指令表示查看目前lfs追蹤那些檔案
```
git lfs track
```

取消追蹤某些檔案
```
git lfs untrack <path-to-file>
```

追蹤完後，記得還是要做git add跟git commit，而且要將其自動產生在當前目錄的.gitattributes也一起add進去，如下圖就是整個上船上去的GitLab的畫面
![](https://hackmd.io/_uploads/HJasmiNfT.png)


## 從repository clone包含lfs的檔案
```
git lfs clone <repo url>
```


## 參考資源
https://www.mankier.com/1/git-lfs-clone
https://guide.ncloud-docs.com/docs/en/sourcecommit-use-lfs
