﻿# ComplexOprationHelper
## 纯Java后台实现区分数据的新增、修改、删除操作
###    原理：
         1. a、添加的数据一般主键id为空;
         2. b、修改的数据拥有主键id不为空;
         3. c、不变的数据toString()结果是相同的;
###      因此,又以上a、b、c三项可以得出如下公式：
         4. >  伪新增的数据 【包含修改的数据】= 新数据 - （新数据 ∩老数据）；
         5. >  伪删除的数据 【包含修改的数据】= 老数据 - (老数据 ∩新数据)；
         6. >   更新的数据  = 伪新增数据 ∩ 伪删除数据；
         7. >   新增的数据 =  伪新增数据  - 更新数据；
         8. >   删除的数据 =  伪删除的数据  - 更新数据；
         
