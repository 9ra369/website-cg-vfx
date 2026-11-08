---
title: "Valerio Viperino氏 — GeoTIFFのDEMデータをHoudiniに持ち込むジオスペーシャルワークフロー"
slug: "valerio-viperino-geospatial-workflows-houdini"
date: 2026-11-08
category: "tutorial"
type: "brief"
tags: ["Houdini", "Python", "GIS", "DEM", "GeoTIFF", "Tutorial"]
topics: ["gis-digitaltwin", "environment"]
tools: ["houdini", "python"]
source_url: [{ "url": "https://valerioviperino.me/houdini/dem/", "label": "Geospatial workflows in Houdini（Valerio Viperino氏のブログ）" }, { "url": "https://github.com/vvzen/Houdini-Geospatial-Tools/blob/main/src/notebooks/Save_GeoTIFF_as_ply.ipynb", "label": "Save_GeoTIFF_as_ply.ipynb（GitHub、解説用ノートブック）" }, { "url": "https://land.copernicus.eu/imagery-in-situ/eu-dem/", "label": "Copernicus EU-DEM（元データの入手先）" }]
language: "英語"
original_post: "https://x.com/kuramaKageya/status/2090000000000000020"
summary: "Valerio Viperino氏が、ヨーロッパ全域の標高データ（Copernicus EU-DEM）をGDALとnumpyで扱いやすいサイズに整え、.plyや16bit PNGとしてHoudiniに読み込むまでの手順をまとめたブログ記事。座標系の変換、4000px程度へのダウンサンプリング、点のランダムサンプリングによる軽量化といった、実際に手を動かすときにつまずきやすい部分が順を追って説明されている。"
ai_confidence: "high"
status: draft
---

![HoudiniでレンダリングしたDEM（標高）データ](images/posts/2090000000000000020-geospatial-00-dem-render.webp)

Valerio Viperino氏のブログ記事「Geospatial workflows in Houdini」を紹介します。2020年末の記事ですが、実際の地形データをHoudiniに持ち込むときの基本が一通り押さえられていて、今読んでも十分参考になります。

![記事のトップ。元のGeoTIFF（16bitにダウンサンプリング）](images/posts/2090000000000000020-geospatial-01-article.webp)

記事の流れは次の通りです。

1. データの入手 — 欧州なら、ESAのCopernicusが公開しているEU-DEMのオープンデータが使える
2. 環境構築 — condaで専用の仮想環境を作り、gdal・numpy・matplotlibなどを入れる
3. 座標系の変換 — 元データのEPSG:3035（ETRS89, LAEA）をgdalwarpでWGS84に変換し、あわせて4000px幅に落として扱いやすくする（変換で縦横比が変わる点にも触れられている）
4. numpyでDEMを読む — 数行で標高値を配列として取り出す。40k × 40kの元データを全画素ポイント化すると約10億点になりHoudiniでは読めないので、画像上に点をランダムに散らして点数を減らす方法を紹介している
5. Houdiniに持ち込む — x, y, zを書き出した`.ply`として読み込む方法と、matplotlibで書き出した16bit PNGをattribfrommapで読む方法の2通り

個人的には、`.ply`のような単純なフォーマットにしておくと後から読み返しやすい、という割り切りと、巨大なDEMを全部は読まずにサンプリングで間引くという考え方がすっと腑に落ちました。GIS側の知識がなくても、コマンドとノートブックを順に追えば同じ結果が再現できる構成になっているのもありがたいです。
（Valerio Viperinoさん、分かりやすいワークフローの公開ありがとうございます）
