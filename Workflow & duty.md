# 前端工作流程

```
当因需求变更而添加、修改了项目文件，我们需要通过下面的几个环节将这一变更更新到线上环境，从而最大程度在上线之前就发现并解决问题：
```

## 一、	理解需求
正常的需求，产品经理会提供产品文档，同时会和相关开发测试进行kickoff会议。当拿到产品文档后，我们需求先进行了解，如果有不能理解的或者觉得有歧义的地方，可以在kickoff会议上提出来。这一步的主要任务就是把本次要开发的需求，全部理解，确保后续开发的功能正确性。

## 二、	核对视觉稿
目前喜地这边会要求设计师除了按产品要求完成设计稿（PSD文件）以外，还会进行设计稿专门的标注。一方面保证了前端工程师在制作时，不会与设计稿出现偏差；一方面也减少了前端工程师需要对照PSD进行一些参数的查看，加快了工作节奏。
这一步的主要任务要求前端在拿到设计稿之后，进行核对。例如设计稿是否有缺少、标注是否完整、与需求功能是否有出入等等，发现问题及时反馈给主管及相关设计师，必要时也许反馈给产品经理。

## 三、	评估工作量和时间
上面两个步骤完成后，前端工程师需要对本次的开发工作进行评估。先评估工作量，例如哪些是页面修改，哪些是新增页面，有多少是需要异步交互的等等。
将功能点列出后，评估相应的时间。时间共分三块：1.静态模板页面制作时间；2.前端脚本功能开发时间；3.与后端联调时间；然后将评估后的时间反馈给前端主管进行审核，审核通过后，按照指定的时间节点进行具体开发工作。

四、	开发
前端人员在完成工作内容的过程中，务必确保需求调整在所有平台、浏览器和设备中均访问正常。
先进行静态页面的制作，如有不需要后端接口配合的交互，也需要在此阶段完成开发。制作完毕后，需要在其电脑上由设计师、产品经理，或相关责任人进行初步确认审核。
审核通过后，需要将静态页面转为模板文件并提交至SVN，交由后端研发进行开发。同时将本次调整中所涉及的静态资源（样式、脚本、图片）通过SPM打包工具发布到开发环境。
如果本次调整中添加了新的页面（例如活动页面），则需要研发人员添加该页面的action——即建立链接、标题、keywords、description，并与新的模板文件进行绑定。
模板提交后，继续进行前端脚本的开发。在开发前，需要与后端工程师进行沟通，合作完成接口文档的编写。脚本开发完成后，最好可以在本地模拟一些数据来验证是否达到预期效果，同时也可以让交互设计师、产品经理进行审核确认。如果实在无法模拟，则需要将本次的确认工作放到下一步的联调环节。

## 五、	联调
如果在联调前，前端人员还有调整过的静态资源（样式、脚本、图片），需要通过SPM打包工具发布到开发环境，并提交SVN。
等后端研发人员的调整也完毕后，通过喜地代码发布平台将这些模板变更以及后端的代码变更统一更新至开发环境。
在确认文件更新到开发环境后，需要由前端人员和研发人员共同检查并确认本次需求调整的更新是否正确且不影响其他网站模块和页面。
根据之前预估的联调时间，前后端人员需要在规定的时间内，完成所有页面、交互功能的调试、验证。
在开发环境中，根据实际情况可能需要再次邀请相关的设计人员、产品经理，或相关责任人做进一步确认。

## 六、	内测
如果是新的项目需求，或是改版优化，在完成联调环节之后，还会将其部署到内测环境，由后端的相关责任人进行内测，发现相关问题并予以处理解决。
如果只是bug修改，则不需要进入此环节。

## 七、	提测
当联调以及内测环节完成之后，由研发人员将本次变更的文件更新到测试环境，并通知测试部门完成测试工作。
如果本次调整中添加了新的页面，则还需要由研发人员将该页面的action添加至测试环境。
在测试部门进行测试的过程中，需要由前端、研发共同跟进并修复在测试过程中发现的新问题。

## 八、	beta验收
当测试人员测试完毕并确认OK后，会将本次的更新部署到beta环境。
在这个环节，测试人员会继续在beta环境确认一遍相关功能和页面的正确性。
这个环节的主要作用就是交由产品、业务和设计人员进行验收，如果存在问题，则需要解决处理并再次更新到beta环境，直到验收完毕。

## 九、	正式上线
当beta环节验收确认后，将会在特定的排期内将其更新到线上环境。
当需求调整更新到线上后，作为前端人员需要及时检查并核对线上展现的正确性。
如果线上环境存在相关问题，则需要及时修复并将修改后的文件再次进行提测和上线处理。

## 十、	线上维护
任何一个版本上线后（尤其是大型项目），在接下来的一周，前端工程师需要每天对线上的页面、功能进行盘查，如果发现问题，需要及时反馈给产品经理及主管，积极配合完成修复工作。


## 备注：
作为工程师，应该养成良好的线上项目盘查习惯。不管是否进行有版本上线，对于自己负责的模块，应该养成每天至少一次的线上盘查工作。保证线上模块正常稳定的运转。

