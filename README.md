代码下载 ====

先安装repo
sudo apt install curl git -y

mkdir ~/bin

PATH=~/bin:$PATH

curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo

chmod a+x ~/bin/repo

如果连接一直失败或下载代码过慢，则使用以下命令:

repo init --repo-url git://github.com/xintiaoxuanlv/repo.git -u git://github.com/omnirom/android.git -b android-9.0 --no-repo-verify


repo sync --no-clone-bundle -c -j4

你希望以后通过 TUNA 同步 AOSP 部分的代码，只需要将 .repo/manifest.xml 把其中的 aosp 这个 remote 的 fetch 从 https://android.googlesource.com 改为 https://aosp.tuna.tsinghua.edu.cn/。

<manifest>

   <remote  name="aosp"
-           fetch="https://android.googlesource.com" 修改前
+           fetch="https://aosp.tuna.tsinghua.edu.cn" 修改后
            review="android-review.googlesource.com" />

   <remote  name="github"
