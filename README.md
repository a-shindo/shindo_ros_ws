# ytlab_ros_evn

## Usage
1. Clone
```
$ git clone git@github.com:Takahashi-Lab-Keio/ytlab_ros_env
```

2. Untrack github
```
$ cd ~/ytlab_ros_env
$ rm -rf .git
その後、好きなパッケージ名に変更して、githubへアップ
```

3. Docker build
```
$ cd ~/ytlab_ros_env/docker
$ ./build.sh
$ ./run.sh
$ cm
exit from container
```

4. Docker run
```
$ cd ~/ytlab_ros_env/docker
$ ./run.sh
```

## 開発方法
* パッケージの説明
    * ディレクトリ
        ~/ytlab_ros_env/ytlab_ros_example
    * パッケージ内のフォルダの役割
        * launch
            * .launchファイルの置き場所
        * rviz
            * .rvizファイルの置き場所
        * scripts
            * pythonスクリプトの置き場所
        * src
            * .h, .cppファイルの置き場所
* ROSパッケージの追加（user_packageというパッケージ名を例として記載）
    1. ~/ytlab_ros_env/以下にuser_packageを追加
    2. ~/ytlab_ros_env/docker/run.shを編集
        * 27行目に下記オプションを追記
            ```
            -v "/$(pwd)/../user_package:/catkin_ws/src/user_package" \
            ```
* ROSパッケージ名の変更（ytlab_ros_exampleをuser_packageへの変更例）
    1. ~/ytlab_ros_env/ytlab_ros_exampleのフォルダ名をuser_packageへ変更
    2. ~/ytlab_ros_env/user_package/package.xml内の全てのytlab_ros_exampleという文字列をuser_packageへ変更
    3. ~/ytlab_ros_env/user_package/CMakeLists.txt内の全てのytlab_ros_exampleという文字列をuser_packageへ変更
    4. ~/ytlab_ros_env/docker/run.sh内の全てのytlab_ros_exampleという文字列をuser_packageへ変更