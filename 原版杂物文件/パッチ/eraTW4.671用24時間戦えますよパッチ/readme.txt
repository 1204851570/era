﻿-------------------------------------------------------------
　　　　　　　eraTW4.671用　２４時間戦えますよパッチ
-------------------------------------------------------------
＝【 動作環境 】＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝

　eraTW4.671

　①バニラの方はそのまま上書きしてください

　②　ＴＷ女子会ver1.12パッチを適用済みの方
　　　→　こちらのパッチで上書きして、ITEM.CSVを適宜書き換えてください

　③　ＴＷ女子会ver1.12パッチはまだ適用してないけどこれからしたい
　　　→　競合のあるCFLAG.CSVだけこちらのパッチのものを上書きしてください

  ※セーブデータのバックアップを取ってからご利用ください。

＝【 概要 】＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝

　眠気覚ましシステムと施肥システムを追加してみました。
　調合道具を何件か追加しました。
　道具使用時、その道具がどんな効果を持つのかを表記するようにしました。
　回復時の表記揺れを改良しました。
　神酒　が利用できるようにしました。

＝【 変更内容 】＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝

(1)　【要睡眠】状態に陥るのを後ろに繰り下げる「眠気覚ましシステム」を搭載
	CFLAG:385,眠気覚まし強度　で利用
	@BEFORETRAIN　で全キャラリセットされる仕組み

	●大回復薬		60分
	●流星群Ｘ	180分
	●破眠薬水	240分
	●万能药　		300分

	上を[道具]で使うと、眠気覚まし効果を発揮します。
　　　　効果は重複しません（薬なので１日にどれか１つしか使えない）。
	MASTER以外の睡眠時間を後ろにずらすことも可能。

	MASTER、TARGETともにinfoに表記されるようになっています。
	難点は睡眠時間が短くなり翌日の体力気力に影響が出ること。あれ、リアル街道？
	睡眠薬とは特に噛ませていません。一応。

(2)　进行調合　の追記と修正
　　　○【流星群Ｘ】の調合指定にミスがあったのを修正。
	　レシピボタンの表記判定が「ストロング虚無」の条件になっていた
	　レシピ１の消費道具指定から「蜂蜜」が漏れていた
　　　○【姜黄飲料】の作成数が２なのに１しか作れていなかったの修正。
	　すみませんでした、見落とし怖い。

　　　○【肥料】【魚粕】【薬水】【魔法薬水】【破眠薬水】の調合の追加
　　　○　他、調合レシピの順番など微修正

(3)　Item.csv　および調合システムに以下の道具を追加。
	195,肥料,1500,
	509,破眠薬水.4000,
	642,魚粕,150,

	507,薬水と508,魔法薬水を実装
	（55,神酒　を解放

　　　○【薬水】【魔法薬水】は気力と『MATERのTSPの回復機能』を持ちます。
　　　○【破眠薬水】は『眠気覚まし』に特化した薬です

(4)　家庭菜園に「施肥」のシステムを追加
	DIM.ERH に　PLANT_FOOD　を追加。肥料の有無の判定に用いる
　　　　（そのうちもっと強力な肥料も追加できるかと…）

	調合で「肥料」を作るか「花屋」で購入し、家庭菜園で撒く。

	植物を収穫するか引っこ抜くまで有効。
	生育するチャンスがあるとき（天候が良好～不順程度）
	PLANT_GROWに補正をかけ、育つ速度を上げる。
　　　　時間をかけないので、時間補正の豊作にはなりにくいですが、回転が良くなるのでトントンかと。
	また、収穫時に作物を入手できる個数を、熟した度合いに応じてランダムに増やす効果もあります。

(5)　[490]道具　を細々改修
	①　道具選択リストを整理し、道具説明を表記するように（だいたいの効果・属性もわかるように）
	②　RECOVER関数との噛み合いで、100以上の回復量の場合は
　　　　　　回復内容が二重表記（最大回復値のあとに実回復値を表記する）になっていたので、
　　　　　　回復値100以下の道具のみ、従来の実回復値の表記を行うようにしました。
　　　　③　回復時に何を使って回復したのかを表記（料理と吃飯の書式にそろえてみました）
	④　【仙丹】が使えない状態のままだったので、自分と相手双方に使える、のほうに追記をしました。
	⑤　【薬水】【魔法薬水】【破眠薬水】の処理を追記しました。
	⑥　眠気覚ましシステムの対象道具に追記、【万能药】の効果にTSP回復も追加

