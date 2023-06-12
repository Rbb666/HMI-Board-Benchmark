# 瑞萨 RA6M3-HMI-Board Benchmark Demo

此仓库为基于RA6M3-HMI-Board开发板，是否开启 GPU 的 A/B 测试仓库。UI Demo 为 LVGL 自带的Benchmark Demo。

* 分支 `use-gpu` 为使用 GPU 版本
* 分支 `unuse-gpu` 为不使用 GPU 版本

测试方法：切换到对应分支，打开 mdk 工程，直接编译下载即可。

测试结果可以参考这篇文档：[RA6M3 LVGL Benchmark 有无GPU跑分对比](https://docs.qq.com/sheet/DZnZUVGNCaXNxU2pt?tab=BB08J2)

| Optimization(OS)                   | GPU(fps) | No GPU(fps) | Prompt ratio(%) |
| ---------------------------------- | -------- | ----------- | --------------- |
| Weight FPS                         | 81       | 55          | 47.27%          |
| Opa speed                          | 91%      | 91%         | 0.00%           |
| Text small                         | 12       | 11          | 9.09%           |
| Text small+opa                     | 13       | 11          | 18.18%          |
| Text medium                        | 13       | 11          | 18.18%          |
| Text medium+opa                    | 13       | 11          | 18.18%          |
| Text large                         | 13       | 11          | 18.18%          |
| Text large+opa                     | 13       | 11          | 18.18%          |
| Text large compressed              | 18       | 15          | 20.00%          |
| Rectangle                          | 123      | 66          | 86.36%          |
| Rectangle+opa                      | 68       | 49          | 38.78%          |
| Rectangle rounded                  | 90       | 57          | 57.89%          |
| Rectangle rounded+opa              | 54       | 41          | 31.71%          |
| Circle                             | 44       | 38          | 15.79%          |
| Circle+opa                         | 32       | 28          | 14.29%          |
| Circle border                      | 37       | 30          | 23.33%          |
| Circle border+opa                  | 35       | 28          | 25.00%          |
| Border                             | 105      | 63          | 66.67%          |
| Border+opa                         | 101      | 63          | 60.32%          |
| Border rounded                     | 90       | 58          | 55.17%          |
| Border rounded+opa                 | 83       | 56          | 48.21%          |
| Border top                         | 93       | 59          | 57.63%          |
| Border top+opa                     | 100      | 62          | 61.29%          |
| Border left                        | 94       | 59          | 59.32%          |
| Border left+opa                    | 99       | 61          | 62.30%          |
| Border top + left                  | 87       | 57          | 52.63%          |
| Border top + left+opa              | 87       | 58          | 50.00%          |
| Border left + right                | 82       | 56          | 46.43%          |
| Border left + right+opa            | 83       | 56          | 48.21%          |
| Border top + bottom                | 85       | 57          | 49.12%          |
| Border top + bottom+opa            | 85       | 56          | 51.79%          |
| Shadow small                       | 35       | 30          | 16.67%          |
| Shadow small+opa                   | 34       | 29          | 17.24%          |
| Shadow small offset                | 35       | 30          | 16.67%          |
| Shadow small offset+opa            | 34       | 27          | 25.93%          |
| Shadow large                       | 23       | 22          | 4.55%           |
| Shadow large+opa                   | 22       | 21          | 4.76%           |
| Shadow large offset                | 23       | 21          | 9.52%           |
| Shadow large offset+opa            | 22       | 21          | 4.76%           |
| Image RGB                          | 252      | 143         | 76.22%          |
| Image RGB+opa                      | 258      | 129         | 100.00%         |
| Image ARGB                         | 159      | 123         | 29.27%          |
| Image ARGB+opa                     | 141      | 109         | 29.36%          |
| Image chorma keyed                 | 148      | 115         | 28.70%          |
| Image chorma keyed+opa             | 129      | 101         | 27.72%          |
| Image indexed                      | 88       | 74          | 18.92%          |
| Image indexed+opa                  | 81       | 68          | 19.12%          |
| Image alpha only                   | 88       | 75          | 17.33%          |
| Image alpha only+opa               | 79       | 72          | 9.72%           |
| Image RGB recolor                  | 143      | 106         | 34.91%          |
| Image RGB recolor+opa              | 120      | 96          | 25.00%          |
| Image ARGB recolor                 | 121      | 94          | 28.72%          |
| Image ARGB recolor+opa             | 111      | 86          | 29.07%          |
| Image chorma keyed recolor         | 108      | 91          | 18.68%          |
| Image chorma keyed recolor+opa     | 103      | 86          | 19.77%          |
| Image indexed recolor              | 75       | 67          | 11.94%          |
| Image indexed recolor+opa          | 68       | 60          | 13.33%          |
| Image RGB rotate                   | 57       | 46          | 23.91%          |
| Image RGB rotate+opa               | 46       | 39          | 17.95%          |
| Image RGB rotate anti aliased      | 29       | 26          | 11.54%          |
| Image RGB rotate anti aliased+opa  | 25       | 23          | 8.70%           |
| Image ARGB rotate                  | 56       | 45          | 24.44%          |
| Image ARGB rotate+opa              | 49       | 41          | 19.51%          |
| Image ARGB rotate anti aliased     | 24       | 21          | 14.29%          |
| Image ARGB rotate anti aliased+opa | 22       | 20          | 10.00%          |
| Image RGB zoom                     | 64       | 51          | 25.49%          |
| Image RGB zoom+opa                 | 53       | 43          | 23.26%          |
| Image RGB zoom anti aliased        | 31       | 28          | 10.71%          |
| Image RGB zoom anti aliased+opa    | 28       | 25          | 12.00%          |
| Image ARGB zoom                    | 61       | 49          | 24.49%          |
| Image ARGB zoom+opa                | 57       | 47          | 21.28%          |
| Image ARGB zoom anti aliased       | 26       | 22          | 18.18%          |
| Image ARGB zoom anti aliased+opa   | 24       | 22          | 9.09%           |
| Text small compressed              | 17       | 15          | 13.33%          |
| Text small compressed+opa          | 17       | 15          | 13.33%          |
| Text medium compressed             | 16       | 14          | 14.29%          |
| Text medium compressed+opa         | 16       | 14          | 14.29%          |
| Text large compressed              | 18       | 15          | 20.00%          |
| Text large compressed+opa          | 18       | 15          | 20.00%          |
| Line                               | 43       | 34          | 26.47%          |
| Line+opa                           | 42       | 34          | 23.53%          |
| Arc think                          | 50       | 39          | 28.21%          |
| Arc think+opa                      | 50       | 39          | 28.21%          |
| Arc thick                          | 51       | 40          | 27.50%          |
| Arc thick+opa                      | 49       | 39          | 25.64%          |
| Substr. rectangle                  | 117      | 68          | 72.06%          |
| Substr. rectangle+opa              | 118      | 68          | 73.53%          |
| Substr. border                     | 117      | 68          | 72.06%          |
| Substr. border+opa                 | 128      | 71          | 80.28%          |
| Substr. shadow                     | 117      | 66          | 77.27%          |
| Substr. shadow+opa                 | 126      | 66          | 90.91%          |
| Substr. image                      | 258      | 168         | 53.57%          |
| Substr. image+opa                  | 247      | 170         | 45.29%          |
| Substr. line                       | 127      | 76          | 67.11%          |
| Substr. line+opa                   | 124      | 76          | 63.16%          |
| Substr. arc                        | 48       | 38          | 26.32%          |
| Substr. arc+opa                    | 49       | 37          | 32.43%          |
| Substr. text                       | 37       | 26          | 42.31%          |
| Substr. text+opa                   | 37       | 27          | 37.04%          |

**Average Prompt**：32.63% 
