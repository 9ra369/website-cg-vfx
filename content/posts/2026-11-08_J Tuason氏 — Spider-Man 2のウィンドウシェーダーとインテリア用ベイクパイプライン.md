---
title: "J Tuason氏 — 『Marvel's Spider-Man 2』の街の窓を支えるウィンドウシェーダーとインテリアのベイクパイプライン"
slug: "j-tuason-spider-man-2-window-shader"
date: 2026-11-08
category: "pipeline"
type: "brief"
tags: ["Houdini", "Shader", "Interior Mapping", "Game", "Technical Art"]
topics: ["environment", "realtime", "pipeline"]
tools: ["houdini"]
source_url: [{ "url": "https://www.artstation.com/artwork/XgVxQL", "label": "Marvel's Spider-Man 2: Window Shader and Pipeline（ArtStation）" }, { "url": "https://www.artstation.com/jtuason", "label": "J Tuason氏のArtStation" }]
language: "英語"
original_post: "https://x.com/kuramaKageya/status/2090000000000000030"
summary: "『Marvel's Spider-Man 2』でウィンドウシェーダーの刷新を担当したJ Tuason氏の解説。奥行きを感じさせるカーテンのバリエーションと、エミッシブなキューブマップを使うパララックスオクルージョン式のインテリア表現を追加し、そのためのHoudiniベースのベイクパイプラインを複数のメンバーとの協力で整えた。"
ai_confidence: "high"
status: draft
---

![パララックスオクルージョン用にベイクされるキューブ状のインテリアのセットアップ](images/posts/2090000000000000030-spiderman2-window-00-cube-interior.gif)

![オクルージョンインテリアシェーダーを適用した平面](images/posts/2090000000000000030-spiderman2-window-01-occlusion-plane.gif)

![ビルのファサードに並ぶ窓のクローズアップ](images/posts/2090000000000000030-spiderman2-window-02-facade.webp)

![夜のニューヨークの街並み](images/posts/2090000000000000030-spiderman2-window-03-night-city.webp)

![昼のニューヨークの街並み](images/posts/2090000000000000030-spiderman2-window-04-day-city.webp)

![Houdiniでのデバッグ用レイヒットの表示](images/posts/2090000000000000030-spiderman2-window-05-houdini-debug-rays.webp)

『Marvel's Spider-Man 2』のウィンドウシェーダーとそのパイプラインについて、J Tuason氏がArtStationで解説しています。

ご本人の説明によると、ウィンドウシェーダーは多くの人の協力で作られたもので、J Tuason氏の担当は、今回のプロジェクト向けにシェーダーを作り直すことでした。具体的には次の2点です。

1. カーテンのバリエーション — 深度オフセットを使って奥行きがあるように見せる
2. パララックスオクルージョンによるインテリア — レイトレーシングのインテリアとは別の手法で、エミッシブなキューブマップを使うため、専用のベイクパイプラインが必要だった

冒頭の2つのGIFは、パララックスオクルージョン用にベイクするキューブ状の部屋のセットアップと、そのテクスチャを使ったオクルージョンインテリアシェーダーを貼った平面の様子です。最後の画像は、James Answer氏が作ったHoudiniのキャプチャで、デバッグ用のレイヒットを表示しています。

パイプライン全体で使われたHDAはJames Answer氏が作成し、エンジンへのカスタム統合とレンダー用の対応をGiacomino Veltri氏が担当、制作アセットに合わせた調整にはXray Halperin氏が参加したとのこと。窓の手法（レイトレーシングとパララックスオクルージョンのインテリア）はJahrain Jackson氏が考案し、カーテンのカスタムインスタンシングはBrandon Shihabi氏がサポートしたそうです。多くのアートディレクターや環境アーティストがインテリアを作ってベイクし、フィードバックを返したとも書かれています。

夜景で窓の1枚1枚に部屋の中が見えているのは、こういう仕組みの積み重ねなのだと思うと面白いです。窓の内側を3Dで作らずに奥行きを出す方法は、街全体を背景として作るときの参考になりそうです。
（J Tuasonさん、分かりやすい解説の公開ありがとうございます）
