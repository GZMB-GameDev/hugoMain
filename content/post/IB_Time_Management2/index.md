+++
date = '2026-03-18T10:32:22+08:00'
draft = true
title = 'CP project Dev Journal 2 - 添加任务预设&修改'

tags = [
    "Time Management",
    "Development Journal"
    
]
categories = [
   "CP Project"
]

+++

### 更新的功能

**>** 允许用户用模板创建任务 <br>
**>** 给予用户更多自定义任务的能力，对子目标进行编辑 <br>
#### 修复了以下问题 <br>
**>**   任务排布过于紧凑 <br>
**>**   修复了添加子目标代码的问题： <br>
```java

    addSubgoalButton.addEventListener('click', function() {
            const name = subgoalNameInput.value.trim();
            const priority = subgoalPrioritySelect.value;
            const estimate = parseInt(subgoalEstimateInput.value);
            const deadline = subgoalDeadlineInput.value;
            
            if (!name) {
                alert('请输入子目标名称');
                return;
            }
            
            if (isNaN(estimate) || estimate <= 0) {
                alert('请输入有效的预计时间');
                return;
            }
            
            if (!deadline) {
                alert('请选择截止日期');
                return;
            }
            
            const goal = goals.find(g => g.id === currentGoalId);
            if (goal) {
                // 检查子目标时间总和是否超过大目标时间
                const subgoalsTotal = goal.subgoals.reduce((total, subgoal) => total + subgoal.estimate, 0);
                if (subgoalsTotal + estimate > goal.estimate) {
                    alert(`子目标总时间（${subgoalsTotal + estimate}小时）已超过大目标时间（${goal.estimate}小时）`);
                    return;
                }
                
                goal.subgoals.push({
                    id: Date.now(),
                    name,
                    priority,
                    estimate,
                    deadline
                });
                renderGoals();
                cancelSubgoal();
            }
        });
    

```


      


### 后续更新

**>** 在电脑上实现定时提醒的功能 <br>




### 项目已经部署至Netlify网址： https://ib-plan-making.netlify.app/

