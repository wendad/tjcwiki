eql eqm eqh
===============================================================

eql-低音衰减(31HZ-125HZ)

eqm-中音衰减(250HZ-2000HZ)

eqh-高音衰减(4000HZ-1600HZ)

(仅x5 x3系列才支持)

上位模拟器不支持

设置范围0-15

0-6为衰减，数字越小衰减越大

8-15为提升，数字越大提升越大

7为平衡，无衰减，无提升

.. attention:: 系统底层是按eq0-eq9的设置来操作的，如果分别修改eql,eqm,eqh等同于分别修改eq0-eq2, eq3-eq6, eq7-eq9；但是修改eq0-eq9并不会影响到eql,eqm,eqh的值。

