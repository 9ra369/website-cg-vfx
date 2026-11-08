---
title: "Matt Estela氏 — CGWiki「Lighting and Shading (Old school style)」Mantra時代のHoudiniライティングとシェーディングのメモ"
slug: "cgwiki-houdini-lighting-shading-old-school"
date: 2026-11-08
category: "tutorial"
type: "brief"
tags: ["Houdini", "Mantra", "Lighting", "Shading", "Redshift", "Tutorial"]
topics: ["lighting-rendering", "lookdev"]
tools: ["houdini"]
source_url: [{ "url": "https://tokeru.com/cgwiki/Houdini_Lighting_Shading.html", "label": "Lighting and Shading (Old school style)（CGWiki）" }, { "url": "https://tokeru.com/cgwiki/", "label": "CGWiki（Matt Estela氏のHoudiniとCGのメモ）" }]
language: "英語"
original_post: "https://x.com/kuramaKageya/status/2090000000000000032"
summary: "Matt Estela氏のCGWikiにある、Mantraを使ったHoudiniの旧来のライティング・シェーディングのワークフローをまとめたページ。テストシーンの作り方、マテリアルの作成と属性によるオーバーライド、AOV（Extra Image Planes）、Renderstate VOP、HDRIを使ったプロジェクション、Redshift、ライトのベイクまでを短いメモ形式で扱っている。"
ai_confidence: "high"
status: draft
---

![CGWikiの「Lighting and Shading (Old school style)」のページ](images/posts/2090000000000000032-cgwiki-00-lighting-shading.webp)

Matt Estela氏のCGWikiから、Houdiniのライティングとシェーディングのページ「Lighting and Shading (Old school style)」を紹介します。

最初に書かれているとおり、このページの大半は現在では古い内容です。Houdiniのライティング・レンダリングは長らく、/objコンテキストでシーンを整理し、ROPでレンダリングし、レンダラにMantraを使う形でしたが、2019年頃からUSDベースのLOPs（Solaris）と新しいレンダラKarmaへ移行していて、Mantraはほぼ役目を終えている、とのことです。ライティングとレンダリングを知りたいだけなら、同じサイトのLopsLightingQuickstartから始めるのがおすすめだと書かれています。それでも今も役立つTipsが残っているので、ページは当面残すそうです。

ページの構成は次の通りです。

1. テストシーンの作成 — 床の上のティーポットにサン・スカイ・カメラを置く最小のシーン
2. レンダーノードの設定とレンダリング
3. マテリアルの作成 — マテリアルパレットからの作成と割り当て
4. マテリアルの属性によるオーバーライド — オブジェクト単位とポイント単位、フェースへのマテリアル割り当て、Cd（ポイントカラー）とアルファ
5. AOV（Extra Image Planes） — シェーダー内でBind Export VOPに接続したものをROP側でAOVとして追加する
6. Mayaの人向けのHoudiniレンダリングの考え方、Renderstate VOP、マテリアルWrangle
7. SDFをサンプリングしたトレイル、HDRIを使ったプロジェクションのセットアップ（MantraとRedshiftのHIPファイルつき）
8. Redshift — ボリュームをライトに反応させる方法、オブジェクトを発光させる方法
9. ライトのベイク

「新しいレンダラを試すときに自分がいつもやる、5分以内のお試しの流れ」として書かれているので、ふだんMantraを使っていなくても、AOVの仕組みやマテリアル属性の渡し方など、レンダラが変わっても通じる考え方が拾えると思います。Solaris以降のワークフローを学ぶ前に、従来のライティングとシェーディングの考え方を知っておくのにも向いていそうです。
（Matt Estelaさん、長年のメモの公開ありがとうございます）
