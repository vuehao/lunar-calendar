# lunar-calendar

> lunar-calendar-vue2  带农历的日历组件 PC端移动端通用

## Build Setup

``` bash
#安装插件
npm install lunar-calendar-vue2 --save

#main 全局引入
import lunar_calendar_vue2 from 'lunar-calendar-vue2'
Vue.use(lunar_calendar_vue2);

#引入组件
<lunar_calendar v-on:choseDay="clickDay"></lunar_calendar>

methods: {
    clickDay (data) { // 选择日期 
        console.log(data);
    }
}

# Attributes
| 属性         | 说明                                                     |  默认  | 是否必传 |
| :---------- | :--------------------------------------------------------| :----: | :------: |
| choseDay    | 选中某天调用的方法，返回选中的日期 YY-MM-DD                 | 无 | 否 |
| changeMonth | 切换月份调用的方法，返回切换到某月的日期 YY-MM-DD            | 无 | 否 |
| isToday     | 切换月份的时候，如果切到当前月份，调用这个方法，返回当前月今天 | 无 | 否 |


# Events
| 属性          | 说明                                      |  默认  | 是否必传 |
| :-------------| :--------------------------------------- | :----: | :------: |
| markDate      | 如果需要某月的几天被标注，传当月的日期数组。 | 空数组 | 否 |
                |  如[2,6,8]当月 2 号 6 号 8 号被会标注（相同的标记） 
| markDateMore  | 需要不同的标记如上Usage 最后一行示例代码    | 空数组 | 否 |
| agoDayHide    | 某个日期以前的不允许点击 时间戳长度是 10 位 |   0    | 否 |
| futureDayHide | 某个日期以后的不允许点击 时间戳长度是 10 位 |  很大  | 否 |

# javascript
在 lunar_calendar标签上添加 ref 属性
例如: <lunar_calendar ref="Calendar"></lunar_calendar>
| 方法           | 说明                                  |
| :------------- | :------------------------------------|
| this.$refs.Calendar.PreMonth() | 调用方法实现转到上个月 |
| this.$refs.Calendar.NextMonth() | 调用方法实现转到下个月|
| this.$refs.Calendar.ChoseMonth('2018-12-12') | 调用方法实现转到某个月 |
| this.$refs.Calendar.ChoseMonth('2018-12-12',false) | 跳转到18年12月12日但是不选中当天,
                                                     | 第二个参数 false表示不选中日期|

```
