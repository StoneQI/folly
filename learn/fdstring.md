<!--
 * @Author: your name
 * @Date: 2021-02-06 22:04:35
 * @LastEditTime: 2021-02-06 22:10:14
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: /folly/learn/fdstring.md
-->


small strings 存放的 size 不是真正的 size，是maxSmallSize - size，这样做的原因是可以 small strings 可以多存储一个字节 。因为假如存储 size 的话，small中最后两个字节就得是\0 和 size，但是存储maxSmallSize - size，当 size == maxSmallSize 时，small的最后一个字节恰好也是\0。