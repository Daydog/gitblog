# [stata](https://github.com/Daydog/gitblog/issues/15)

善用do editor
window-->do-file editor，打开do编辑器，将常用命令写入，另存为示例如下
```
global id id
global t t
global ylist SR
global xlist TEN DUA OWN FAM REM BC TEN_BC DUA_BC OWN_BC FAM_BC REM_BC

describe $id $t $ylist $xlist
summarize $id $t $ylist $xlist

* Set data as panel data
sort $id $t
xtset $id $t
xtdescribe
xtsum $id $t $ylist $xlist

* interactive
gen TEN_BC = TEN * BC
gen DUA_BC = DUA * BC
gen OWN_BC = OWN * BC
gen FAM_BC = FAM * BC
gen REM_BC = REM * BC

* Pooled OLS estimator
reg $ylist $xlist

* Population-averaged estimator
xtreg $ylist $xlist, pa

* Fixed effects or within estimator
xtreg $ylist $xlist, fe

* Random effects estimator
xtreg $ylist $xlist, re theta

* Breusch-Pagan LM test for random effects versus OLS
quietly xtreg $ylist $xlist, re
xttest0

* Hausman test for fixed versus random effects model
quietly xtreg $ylist $xlist, fe
estimates store fixed
quietly xtreg $ylist $xlist, re
estimates store random
hausman fixed random

* correlation analysis
logout, save(xxx) word replace: pwcorr_a

```