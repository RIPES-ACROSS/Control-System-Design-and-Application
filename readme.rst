********************************************
制御系の設計と応用
********************************************

本レポジトリは，講義の補助資料として用いる．

ソースコードは全てJupyter notebookで記述されている．
トップディレクトリ以下に内容ごとにまとまっているディレクトリが存在し，ここのサブディレクトリ内を1回の授業の目安とする．
Jupyter実行環境において，notebookを開いた後にShift+Enterを押していくことで，セル単位で実行が可能である．
Jupyter環境は，(1)既に環境構築が済んでいるものを使うか，(2)自前で環境構築するかの2通りがある．
前者はGoogle colab，後者はdockerコンテナをお勧めする．

See also:

- https://www.youtube.com/watch?v=jZ952vChhuI
- https://www.youtube.com/watch?v=inN8seMm7UI
- http://colab.research.google.com/
- https://jupyter-docker-stacks.readthedocs.io/en/latest/index.html


Dockerの使い方
*****************************************

#. Docker Desktop for Windowsをインストールする
#. WindowsであればPowershellあるいはWindows terminalから下記コマンドを打つことで，gitレポジトリからファイルを取得し，dockerを立ち上げる．

.. code-block::

    cd Documents/Github
    git clone git@github.com:RIPES-ACROSS/Control-System-Design-and-Application.git
    cd Control-System-Design-and-Application
    docker run --rm -v ${PWD}:/home/jovyan/repos -p 8888:8888 jupyter/scipy-notebook:latest

#. ブラウザから"http://localhost:8888/lab"へアクセスし，jupyter上のreposディレクトリにアクセスすることで，配布したJupyterノートブックをShift+Enterで実行できる．
#．dockerを止めたい場合は，docker psで走っているプロセスIDを確認して，docker stop [ID]か，下記のコマンドで一括停止する．なお，PCを再起動してもdockerコンテナは停止する．

.. code-block::

    docker stop $(docker ps -q)

See also:

- https://hub.docker.com/r/jupyter/scipy-notebook
- https://docs.docker.com/docker-for-windows/install/
- https://docs.docker.com/docker-for-windows/
- https://docs.docker.com/engine/reference/commandline/cli/
- https://github.com/microsoft/terminal