## 本项目实现的最终作用是基于SSH学生请假管理系统
## 分为3个角色
### 第1个角色为管理员角色，实现了如下功能：
 - 公告管理
 - 学生管理
 - 班主任管理
 - 班级管理
 - 留言板管理
### 第2个角色为教师角色，实现了如下功能：
 - 学生管理
 - 审批学生请假
 - 教师角色登录
 - 请假查看
### 第3个角色为学生角色，实现了如下功能：
 - 学生登录
 - 我的请假
 - 留言板
 - 请假申请
## 数据库设计如下：
# 数据库设计文档

**数据库名：** ssh_stu_qingjiasys

**文档版本：** 


| 表名                  | 说明       |
| :---: | :---: |
| [t_classroom](#t_classroom) |  |
| [t_comment](#t_comment) |  |
| [t_manage](#t_manage) |  |
| [t_noteinfo](#t_noteinfo) |  |
| [t_noticeinfo](#t_noticeinfo) |  |
| [t_student](#t_student) | 学生信息表 |

**表名：** <a id="t_classroom">t_classroom</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | college |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  3   | isDelete |   int   | 10 |   0    |    N     |  N   |       |   |
|  4   | major |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  5   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 名字  |

**表名：** <a id="t_comment">t_comment</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | content |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 内容  |
|  3   | createTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 创建时间  |
|  4   | student_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 学生ID  |
|  5   | isDelete |   int   | 10 |   0    |    N     |  N   |       |   |

**表名：** <a id="t_manage">t_manage</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | isDelete |   int   | 10 |   0    |    N     |  N   |       |   |
|  3   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 名字  |
|  4   | password |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 密码  |
|  5   | realname |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 真实名字  |
|  6   | type |   int   | 10 |   0    |    N     |  N   |       | 类型  |
|  7   | classRoom_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="t_noteinfo">t_noteinfo</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | createTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 创建时间  |
|  3   | endTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 结束时间  |
|  4   | startTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 开始时间  |
|  5   | status |   int   | 10 |   0    |    N     |  N   |       | 状态  |
|  6   | title |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 标题  |
|  7   | type |   int   | 10 |   0    |    N     |  N   |       | 类型  |
|  8   | student_id |   int   | 10 |   0    |    Y     |  N   |   NULL    | 学生ID  |
|  9   | isDelete |   int   | 10 |   0    |    N     |  N   |       |   |
|  10   | content |   longtext   | 2147483647 |   0    |    Y     |  N   |   NULL    | 内容  |

**表名：** <a id="t_noticeinfo">t_noticeinfo</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | content |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 内容  |
|  3   | createTime |   datetime   | 19 |   0    |    Y     |  N   |   NULL    | 创建时间  |

**表名：** <a id="t_student">t_student</a>

**说明：** 学生信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | isDelete |   int   | 10 |   0    |    N     |  N   |       |   |
|  3   | name |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 名字  |
|  4   | password |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 密码  |
|  5   | realname |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 真实名字  |
|  6   | sex |   int   | 10 |   0    |    N     |  N   |       | 性别  |
|  7   | xh |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  8   | classRoom_id |   int   | 10 |   0    |    Y     |  N   |   NULL    |   |

