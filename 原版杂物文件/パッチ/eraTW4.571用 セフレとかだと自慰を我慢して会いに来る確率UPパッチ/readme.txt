一日の終わりに欲求不満だとオナったり、我慢して抱いてもらいに来るけど
炮友なら自慰より抱いてもらいにやって来る方がそれらしいんじゃないかってことで作成。

[内容]
一日の終わりの自慰タイムにて
你との関係性によって自慰を我慢して、你の住んでいるところに訪問する確率が上がります。

愛欲 > 恋慕 > 炮友、愛人 > 思慕 の順で確率UP


一応動作確認ver : eraTW4.571


[更新履歴]
2018/01/08	適当に完成


[既存ファイル変更点＆自分用メモ]
AFTERTRA.ERB
404行	ELSEIF CFLAG:LOCAL:积攒度 > 自慰発生閾値
の下に
		LOCAL:1 = 0
		IF TALENT:LOCAL:愛欲
			LOCAL:1 = 5
		ELSEIF TALENT:LOCAL:恋慕
			LOCAL:1 = 4
		ELSEIF TALENT:LOCAL:炮友
			;愛人もここ
			LOCAL:1 = 3
		ELSEIF TALENT:LOCAL:思慕
			LOCAL:1 = 2
		ENDIF
		IF TALENT:LOCAL:自制心 && LOCAL:1 < 5
			LOCAL:1 += 1
		ENDIF
		IF CFLAG:LOCAL:既成事実 & 合意_诶嘿嘿 && !RAND:(7 - LOCAL:1)
を追加
