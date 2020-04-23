﻿日历バグFIX

○ファイル構成
 ERB┬MOVEMENTS─JOB_仕事内容.ERB
    └指令関連─日历.ERB

○修正内容
　日历呼び出し時に条件を満たしているキャラクターの
　仕事予定が表示されないことがある問題を修正

○修正箇所
・JOB_仕事内容.ERB
　@CHARA_HOLIDAY
　①@CHARA_HOLIDAY(ARG)の引数を増やして（省略可）
　　@CHARA_HOLIDAY(ARG, ARG:1=0)に変更
　②13-16行目をARG:1の値による分岐で回避するよう修正
　　ARG:1 = 1の場合、工作量による休日判定と、
　　終了時刻による休日判定を行わない
・日历.ERB
　@予定表
　①209行目のCHARA_HOLIDAYの呼び出しに引数を追加
　　CHARA_HOLIDAY(LOCAL, 1)

by eratoho総合スレ240-585

