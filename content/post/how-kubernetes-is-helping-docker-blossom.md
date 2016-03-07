+++
date = "2016-03-05T16:54:34+09:00"
draft = false
title = "いかにして Kubernetes は Docker を補うか"

+++

(この記事は「[How Kubernetes is helping Docker blossom](https://opensource.com/business/16/1/scale14x-interview-jason-brooks-red-hat)」の翻訳です)

![いかにして Kubernetes は Docker を補うか](/images/posts/2016-03-kubernetes/containers_2015-1-osdc-lead.png)

[Kubernetes](http://kubernetes.io/) と [Docker](https://www.docker.com/) は、いずれもソフトウェア業界におけるキーワードとなっています。ビジネスやコンピュータに熱心な人たちはコンテナ技術についてさらに深く学ぼうとしています。

幸いなことに Red Hat でソフトウェア・アナリストをしている [Jason Brooks](https://twitter.com/jasonbrooks) に、コンテナ技術の最新動向について聞くことができました。彼は [SCaLE 14x](https://opensource.com/resources/scale-14x) で Kubernetes について話す予定です。

![QA](/images/posts/2016-03-kubernetes/Interview-banner-QA.png)

### すでに Docker に馴染みがあり、これから Kubernetes を学ぼうとしている人たちに何を伝えたいですか?

Kubernetes は Docker を複数ホストでの運用に拡張します。(Docker 関連のプロジェクトは全てそうですけど) Kubernetes は比較的新しいプロジェクトです。一方で、 Google の長年におけるコンテナ運用技術の結晶でもあります。この出自にも関わらず、Kubernetes は多くのコントリビュータによって支えられており、結果として様々なユースケースやアイディアが反映されたプロジェクトとなっています。ローカル環境で試しに触ってみたければ、[こちらの記事](https://github.com/kubernetes/kubernetes/blob/release-1.1/docs/getting-started-guides/docker.md)を参考にしてください。

### Kubernetes はホビー・プログラマが開発しているのでしょうか? それとも大企業が自社のために開発しているのでしょうか?

これについて詳しく調べたことはありません。私が言えるのは Kubernetes は様々な種類のアプリケーションに適用可能だということです。私自身も大企業で働いていますが、SCaLE で話すユースケースは大企業だけにあてはまるものではありません。

### Kubernetes はクラスタ環境におけるコンテナ化されたアプリケーションのデプロイとスケーラビリティのためのツールですね。これはコンテナの流行にどう関連しているのでしょうか?

Docker をコンテナ運送に例えるのは魅力的なアイディアです。しかし、コンテナだけでは運河を渡り切ることはできません。コンテナの流行を一過性のものでなくするためには、コンテナを開発者のノートパソコンからプロダクションに移してあげる必要があります。この作業に Kubernetes が一役買ってしているのです。

### Kubernetes には将来的に、どのような技術が組み込まれるでしょうか?

可能性は無限大です。SCaLE ではこのことも話そうと思います。分散ストレージや仮想化もその一部です。これらの技術はコンテナとは関係ないように思えるかもしれません。しかし複数のマシンを柔軟に使いたいとは思いますよね (だから、こういうものが欲しくなりますよね)。

### Kubernetes は多くのプラットフォームで動作しますね。マルチプラットフォームの実現はどのくらい大変なのですか?

これについては、たくさんのコントリビュータが手伝ってくれています。コントリビュータごとに、気にかけるプラットフォームやユースケースが違うのです。結果として、多くのプラットフォームがサポートされています。

### これらの環境をテストするための自動化されたセットアップ手順はありますか?

全ての環境を試してみたわけではありませんが、通常は [Fedora](https://getfedora.org/) や [CentOS](https://www.centos.org/) による[Atomic](http://www.projectatomic.io/download/) プロジェクト、そして [Ansible](http://ansible.com/) や [Vagrant](https://www.vagrantup.com/) で環境構築の自動化をしています。([くわしくはこちら](http://www.projectatomic.io/blog/2015/09/clustering-atomic-hosts-with-kubernetes-ansible-and-vagrant/))。

### この数年間で Kubernetes はどのように進化するでしょうか? 大きな目標はありますか?

短期的には [SELinux](https://en.wikipedia.org/wiki/Security-Enhanced_Linux) に関する問題解決と Kubernetes コンポーネント自身をコンテナの中で動かすことです。また、複数のコンテナ・エンジンのサポートや、[Mesos](http://mesos.apache.org/) などの他のリソース管理ツールとの協調にも興味があります。

### SCaLE 14x Series

SCaLE はコミュニティにより運営されている、オープンソースまたはフリーソフトウェアに関する北アメリカの大規模カンファレンスです。「The Scale 14x」シリーズでは、スピーカーとしての登壇が予定されている方に、イベントに先駆けてインタビュー記事を掲載しています。

### ライセンス

原文は [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/) で提供されています。本記事も同ライセンスに従います。
