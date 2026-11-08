---
title: "TimJ氏 — Houdini×Redshiftでマクロ撮影風の環境を作る4時間のチュートリアル"
slug: "timj-macro-environment-design-houdini"
date: 2026-11-08
category: "tutorial"
type: "brief"
tags: ["Houdini", "Redshift", "Vellum", "Procedural Modeling", "Environment", "Tutorial"]
topics: ["environment", "fx", "lookdev"]
tools: ["houdini"]
source_url: [{ "url": "https://www.cgcircuit.com/tutorial/macro-environment-design-in-houdini", "label": "Macro Environment Design in Houdini（CGCircuit、$60）" }, { "url": "https://timj-design.com/", "label": "TimJ氏のサイト" }]
language: "英語"
original_post: "https://x.com/kuramaKageya/status/2090000000000000028"
summary: "TimJ氏がCGCircuitで公開している「Macro Environment Design in Houdini」。Houdiniのプロシージャル技術でマクロ撮影のような静止画・アニメーションを作る約4時間（全15本）の講座で、岩のベースジオメトリから抽象的な「ブロブ」、Vellumによるグレインと細い葉のシミュレーション、Redshiftでのルックデブとレンダリングまでを解説している。"
ai_confidence: "high"
status: draft
---

![「Macro Environment Design with TIMJ」のタイトル画像](images/posts/2090000000000000028-macro-00-cover.webp)

TimJ氏の「Macro Environment Design in Houdini」を紹介します。CGCircuitで配信されている講座で、HoudiniとRedshiftを使い、マクロレンズで撮ったような画をプロシージャルに作っていきます。

講座の説明によると、基本のジオメトリをゼロから作ったあと、より抽象的な「ブロブ」に進み、最後にRedshiftでルックデブとレンダリングまで行うとのこと。全4章・15本で、合計4時間1分です。

1. Foundation Setup / Procedural Rock Geometry Creation（4本） — ベースの作成、VDBリメッシュとディテール追加、土台のR&D
2. The "Blob" Setup（3本） — ブロブのマスクと配置、ループとVellum、VOPsによるカスタムディスプレイスメント
3. Vellum Grain and Thin Leaf Setup（2本） — Vellumのグレインシミュレーション、細い葉のためのVellumヘアシミュレーション
4. Look Development and additional Processing / Outro（6本） — ルックデブの下準備とゴボ、石とブロブのRedshiftマテリアル、Megascansを使った新しいセットアップとレンダリング、カメラの遷移とアニメーション

難易度は中級〜上級で、価格は単品$60、またはCGCircuitの月額メンバーシップ（$49/月）に含まれます。2022年3月の公開で、2025年9月にも更新されているそうです。

Vellumのグレインやヘアを「岩」や「葉」のようなスケールの小さい被写体に使い、被写界深度の浅いマクロの画に仕上げていく流れが面白そうです。Houdiniでの環境制作というと大きな地形が思い浮かびますが、こういう小さな世界の作り方も参考になると思います。
（TimJさん、貴重な講座の公開ありがとうございます）
