---

copyright:
  years: 2017
lastupdated: "2017-3-16"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# 컴포지트 파이프라인의 배치 플랜 사용자 정의
{: #tasks_overview}

컴포지트 파이프라인의 배치 플랜에서 태스크는 소프트웨어 배치와 연관된 비즈니스상 의미 있는 일부 활동을 표시합니다. 태스크는 배치 플랜에서 정의됩니다. 

{:shortdesc}

대부분의 태스크에는 시작점, 끝점 및 측정 가능한 기간이 있습니다. 태스크의 유형은 다음 중 하나일 수 있습니다. 

<ul>
<li>수동 태스크는 소프트웨어 배치와 연관된 활동을 표시할 수 있습니다(예: 오프라인으로 서버 설정 또는 데이터베이스 업데이트). </li>
<li>UrbanCode Deploy 태스크는 IBM&reg; UrbanCode&reg; Deploy 앱을 표시합니다. 사용자는 IBM UrbanCode Deploy 유형 태스크의 IBM UrbanCode Deploy 앱을 실행할 수 있습니다. </li>
<li>Continuous Delivery Pipeline 태스크는 {{site.data.keyword.contdelivery_full}}의 일부인 {{site.data.keyword.deliverypipeline}}의 인스턴스를 표시합니다. 이 태스크 유형의 {{site.data.keyword.deliverypipeline}}의 인스턴스를 관리할 수 있습니다. </li>
<li>지연 태스크는 특정 시간에 발생하는 중요 이벤트를 표시합니다. </li>
<li>헤더 태스크는 구성 요소입니다. 예를 들어, 헤더 태스크를 사용하여 태스크 그룹을 식별할 수 있습니다. </li>
</ul>

<!-- You can add tasks to deployment plans by creating tasks or you can import tasks from CSV files that are created by IBM UrbanCode Release or another application. You can also copy tasks from other deployment plans. See [Importing tasks](/docs/services/UCCR/UCCR_deployPlan.html#plan_importTasks) for information about the format of the CSV file. -->

## 태스크 작성
{: #tasks_create}

태스크를 작성할 때 사용자는 태스크가 추가될 배치 플랜을 선택합니다. 기본적으로 새 태스크는 배치 플랜의 끝에 삽입됩니다. 태스크가 작성되면 이를 이동하거나 복사하고 이를 다른 배치 플랜에 붙여넣을 수 있습니다. 기타 [태스크](/docs/services/ContinuousDelivery/pipeline_deployment_plan.html#tasks_dependencies)의 종속 항목을 작성할 수도 있습니다. 

태스크가 저장되면 조치 아이콘이 태스크에 대해 표시됩니다. 조치 아이콘을 사용하여 배치 중에 태스크의 상태를 변경할 수 있습니다. 모든 태스크에는 **건너뛰기** 조치 아이콘이 있습니다. **시작** 등의 기타 아이콘은 컨텍스트가 이에 적합할 때 표시됩니다. 

![](../UCCR/images/deploy-plan-intro.png "일반 배치 플랜")

*그림 1. 태스크 및 조치 아이콘이 있는 단순 배치 플랜*

배치 플랜의 각 태스크는 별도 행에 포함되어 있습니다. 각 태스크에 대해 표시된 정보는 다음 표에 설명되어 있습니다. 

### 표 1. 태스크 특성

| 특성  | 설명  |
| ------------------ | ------------------ |
| 이름               |태스크 이름       |
| 유형               |태스크 유형: 수동, Continuous Delivery Pipeline, 지연, 이메일, 헤더/참고, UrbanCode Deploy|             
| 상태             |태스크 상태: 시작되지 않음, 완료됨, 실패함, 건너뜀, 적용 불가능 |
| 소유자              |태스크가 지정된 사용자                                                        |
| 시작 시간  |시작 시간 또는 스케줄된 시작을 기반으로 하는 예상 시작 시간 또는 기타 태스크의 추정 기간        |
| 종료 시간               |태스크가 종료된 시간        |
| 기간               |태스크 시작에서 태스크 종료까지의 기간(분 단위)        |
| 종속 항목 수               |태스크의 전제조건 및 태스크의 종속자인 태스크의 수        |

---
태스크가 배치 플랜에 추가되면 다양한 방법으로 이를 관리할 수 있습니다.

   * 태스크를 이동하려면 이를 새 위치로 끌어오십시오. 

   * 태스크 또는 그룹을 복사하려면 태스크를 클릭하고 **복사** 아이콘 <img class="inline" src="../UCCR/images/copy-group.png"  alt="복사 아이콘">을 클릭한 후에 복사된 태스크가 삽입될 위치에 커서를 올려놓고 **붙여넣기** 아이콘 <img class="inline" src="../UCCR/images/paste-group.png"  alt="붙여넣기 아이콘">을 클릭하십시오. 

   * 배치 플랜에서 태스크 또는 그룹을 잘라내려면 태스크를 클릭하고 **잘라내기** <img class="inline" src="../UCCR/images/cut-group.png"  alt="잘라내기 아이콘">을 클릭하십시오. 

   * 태스크를 삭제하려면 이를 클릭하고 **삭제** <img class="inline" src="../UCCR/images/trash-group.png"  alt="삭제 아이콘">을 클릭하십시오. 태스크가 배치 플랜에서 제거됩니다. 

<!-- ## Creating UrbanCode Deploy tasks
{: #tasks_UDTasks}

UrbanCode Deploy tasks manage UrbanCode Deploy applications. When you run an UrbanCode Deploy task, the associated UrbanCode Deploy application runs by using the process, version, and environment specified by the task. You can set the version and environment at design time or wait and select them at run time.

During deployments, UrbanCode Deploy tasks start automatically when they become eligible to run.   

**Important** Applications become available after {{site.data.keyword.uccr_short}} is integrated with UrbanCode Deploy. The applications that are available to a deployment plan depend on the team that is assigned to the plan. The applications that are managed by the team in UrbanCode Deploy are also available in {{site.data.keyword.uccr_short}}.

Complete the following tasks to create an UrbanCode Deploy task.

1. On the Deployment Plan Details page, click **Create Task**. If you want to insert a task at a specific position in the plan, select a task before using the **Create Task**. The new task is inserted above the selected task.

1. On the Create Task dialog box, in the **Type** list, select **UrbanCode Deploy**.

1. In the **Name** field, enter a name for the task.

3. In the **Duration (minutes)** field, enter the number of minutes that you expect the task to run until it is completed. The estimated duration is used to calculate expected deployment times.

3. In the **Tags** list, attach a tag to the task. You can select multiple tags. To create a tag, type the tag name in list's text field.

3. In the **Application Name** list, select an application.

3. In the **Process** list, select an application process. Processes that belong to the selected UrbanCode Deploy application are available.

3. In the **Environment** list, select an application environment. Environments that belong to the selected UrbanCode Deploy application are available.  To postpone selecting an environment until you are ready to run the deployment, select **Use Version Tab**.

3. In the **Version** list, select an application version. Versions refer to IBM UrbanCode Deploy application snapshots. Versions that belong to the selected application are available.  To postpone selecting a version, select **Use Version Tab**. If the application process does not require a version, select **No Version**. You might select this last option if you are running a configuration-type process that does not require components.

3. In the **Assigned groups and users** list, assign the task to a user or group. The assigned user runs the task during deployment.

3. In the **Owner** list, select the task owner. The default owner is the user who created the task. The **Owner** list is displayed after the task is assigned to a user or group.    

5. Click **Save**. The task is inserted into the deployment plan.

After the task is created, the plan's **Version** tab is updated with information about the application assigned to the task. If you selected **Use Version Tab** for the application environment and version, use the Version tab to set those options before running the deployment. -->

## 수동 태스크 작성
{: #tasks_manual}

일반적으로 수동 태스크는 시작점, 끝점 및 측정 가능한 기간이 있는 소프트웨어 릴리스와 연관된 일부 활동을 표시합니다. 

수동 태스크를 작성하려면 다음 단계를 따르십시오.

1. 배치 플랜 세부사항 페이지에서 **태스크 작성**을 클릭하십시오. 플랜의 특정 위치에서 태스크를 삽입하려면 **태스크 작성**을 클릭하기 전에 태스크를 선택하십시오. 새 태스크가 선택된 태스크 위에 삽입됩니다. 

1. 태스크 작성 창의 **유형** 목록에서 **수동**을 선택하십시오. 

1. **이름** 필드에서 태스크의 이름을 입력하십시오.

3. **기간(분)** 필드에서 태스크가 완료될 때까지 태스크 실행의 예상 기간(분)을 입력하십시오. 예상 기간은 예상 배치 시간을 계산하는 데 사용됩니다. 

3. **태그** 목록에서 태스크에 태그를 첨부하십시오. 여러 개의 태그를 선택할 수 있습니다. 태그를 작성하려면 목록의 텍스트 필드에서 태그 이름을 입력하십시오. 

3. **지정된 그룹 및 사용자** 목록에서 사용자 또는 그룹에 태스크를 지정하십시오. 지정된 사용자는 배치 중에 태스크를 실행합니다. 

3. **소유자** 목록에서 태스크 소유자를 선택하십시오. 기본 소유자는 태스크를 작성한 사용자입니다. **소유자** 목록은 태스크가 사용자 또는 그룹에 지정된 후에 표시됩니다.     

5. **저장**을 클릭하십시오. 태스크가 배치 플랜에 삽입됩니다. 

## 지연 태스크 작성
{: #tasks_delayed}

지연-유형 태스크는 배치 중의 마일스톤 또는 중요한 이벤트를 표시합니다. 지연 태스크에서 사용자는 중요한 태스크가 예상된 시간에 시작하도록 보장할 수 있습니다. 일반적으로 지연 태스크는 기타 중요한 태스크의 전제조건입니다. 

지연 태스크는 실행 자격을 갖는 순간 시작되며, 이는 사용자가 지정한 시간에 완료됩니다. 시작된 지연-유형 태스크의 상태는 계획된 시간에 도달될 때까지 "진행 중"이며, 이에 도달되면 상태가 "완료됨"으로 변경됩니다. 지연 태스크가 완료되면 이에 종속된 태스크가 실행을 시작합니다. 

지연 태스크를 작성하려면 다음 단계를 따르십시오.

1. 배치 플랜 세부사항 페이지에서 **태스크 작성**을 클릭하십시오. 플랜의 특정 위치에서 태스크를 삽입하려면 **태스크 작성**을 클릭하기 전에 태스크를 선택하십시오. 새 태스크가 선택된 태스크 위에 삽입됩니다. 

1. 태스크 작성 창의 **유형** 목록에서 **지연**을 선택하십시오. 

1. **이름** 필드에서 태스크의 이름을 입력하십시오.

3. **시간** 필드에서 태스크가 완료될 시간을 입력하거나 선택하십시오. 

3. **시간대** 목록에서 **시간** 필드에 입력한 값의 시간대를 선택하십시오.     

5. **저장**을 클릭하십시오. 태스크가 배치 플랜에 삽입됩니다. 

## 헤더 태스크 작성
{: #tasks_header}

헤더 태스크는 배치 플랜에 추가될 수 있는 구성 요소를 표시합니다. 태스크 그룹을 작성하는 경우, 헤더 태스크의 그룹을 식별할 수 있습니다. 헤더 태스크에는 기타 태스크와 같은 종속 항목이 있을 수 있습니다. 

<!-- When you import a deployment plan from IBM UrbanCode Release, segment tasks are bracketed by note-type Start Segment and End Segment tasks. Segment dependencies are represented by dependencies to End Segment tasks. -->

헤더 태스크를 작성하려면 다음 단계를 따르십시오.

1. 배치 플랜 세부사항 페이지에서 **태스크 작성**을 클릭하십시오. 플랜의 특정 위치에서 태스크를 삽입하려면 **태스크 작성**을 클릭하기 전에 태스크를 선택하십시오. 새 태스크가 선택된 태스크 위에 삽입됩니다. 

1. 태스크 작성 창의 **유형** 목록에서 **헤더**를 선택하십시오. 

1. **이름** 필드에서 태스크의 이름을 입력하십시오. 이름은 태스크 그룹 이름을 표시할 수 있습니다. 

3. **설명** 필드에서 설명을 입력하거나 붙여넣으십시오. 참고, 리마인더 또는 기타 지시사항을 입력할 수 있습니다. 

5. **저장**을 클릭하십시오. 태스크가 배치 플랜에 삽입됩니다. 

## Delivery Pipeline 태스크 작성
{: #tasks_pipelineCD}

{{site.data.keyword.contdelivery_short}} 서비스에서 {{site.data.keyword.deliverypipeline}}은 DevOps 워크플로우를 자동화합니다. 사용자는 파이프라인 태스크에서 {{site.data.keyword.deliverypipeline}}의 인스턴스를 관리할 수 있습니다. 

Delivery Pipeline 태스크를 작성하려면 다음 단계를 따르십시오. 

1. 배치 플랜 세부사항 페이지에서 **태스크 작성**을 클릭하십시오. 플랜의 특정 위치에서 태스크를 삽입하려면 **태스크 작성**을 클릭하기 전에 태스크를 선택하십시오. 새 태스크가 선택된 태스크 위에 삽입됩니다. 

1. 태스크 작성 창의 **유형** 목록에서 **Continuous Delivery Pipeline**을 선택하십시오. 

1. **이름** 필드에서 태스크의 이름을 입력하십시오. 이름은 태스크 그룹 이름을 표시할 수 있습니다. 

3. **설명** 필드에서 설명을 입력하거나 붙여넣으십시오. 참고, 리마인더 또는 기타 지시사항을 입력할 수 있습니다. 

3. **파이프라인 ID** 필드에서 파이프라인 ID를 입력하거나 붙여넣으십시오. 

3. **단계 이름** 필드에서 단계 이름을 입력하거나 이를 붙여넣으십시오. 

5. **저장**을 클릭하십시오. 태스크가 배치 플랜에 삽입됩니다. 

## 태스크 그룹 관리
{: #tasks_groups}

둘 이상의 태스크를 태스크 그룹에 결합할 수 있습니다. 그룹을 작성할 때 사용자는 그룹의 실행 패턴(순차 또는 병렬)을 정의합니다. 임의의 순서로 병렬 패턴 그룹의 태스크를 실행할 수 있으며, 종속 항목이 존재하지 않으면 태스크를 동시에 실행할 수 있습니다. 순차 그룹의 태스크는 첫 번째 또는 맨 위 태스크에서 시작하여 목록 순서대로 완료됩니다. 

그룹을 기타 그룹 내에 임베드할 수 있습니다. 병렬-패턴 그룹 내에 순차-패턴 그룹을 임베드할 수 있으며, 그 반대도 가능합니다. 그러나 다른 순차 그룹 내에 순차-패턴 그룹을 임베드할 수는 없습니다. 또는 다른 병렬 그룹 내에 병렬-패턴 그룹을 임베드할 수도 없습니다.   

태스크 그룹을 작성하려면 다음 단계를 따르십시오.

1. 배치 플랜 세부사항 페이지에서 둘 이상의 태스크를 선택하십시오. 

1. 작성할 그룹의 유형에 따라 다음 단계 중 하나를 완료하십시오. 

  <ul>
  <li>병렬 그룹을 작성하려면 **병렬** 아이콘 <img class="inline" src="../UCCR/images/para-icon.png"  alt="병렬 그룹 아이콘">을 클릭하십시오. 선택된 태스크에서 병렬 그룹을 작성할 수 없으면 아이콘이 사용되지 않습니다. 예를 들어, 선택된 모든 태스크가 이미 병렬 그룹에 있으면 병렬 그룹을 작성하지 못할 수도 있습니다.
  </li>
  <li>순차 그룹을 작성하려면 **순차** 아이콘 <img class="inline" src="../UCCR/images/seq-icon.png"  alt="순차 그룹 아이콘">을 클릭하십시오.
  </li>
  </ul>

그룹이 작성되며 그룹 선택 표시줄이 배치 플랜에 추가됩니다. 인접하지 않은 태스크를 선택한 경우, 태스크는 맨 위의 선택된 태스크에서 시작되는 인접 목록을 작성합니다. 

다음 그림은 병렬 그룹을 표시합니다. 그룹 선택 표시줄은 그룹의 유형(병렬 <img class="inline" src="../UCCR/images/para-select.png"  alt="병렬 그룹 선택"> 또는 순차 <img class="inline" src="../UCCR/images/seq-select.png"  alt="순차 그룹 선택">)을 식별합니다. 

(![](../UCCR/images/group-select.png "일반 배치 플랜"))

*그림 2. 병렬 그룹*

그룹을 이동하려면 **그룹 선택 표시줄**을 클릭하거나 그룹의 임의의 위치를 클릭하고 이를 새 위치로 끌어오십시오. 

그룹을 복사하려면 그룹을 선택하고 **복사** 아이콘 <img class="inline" src="../UCCR/images/copy-group.png"  alt="복사 아이콘">을 클릭한 후에 복사된 그룹이 삽입될 위치에 커서를 올려놓고 **붙여넣기** <img class="inline" src="../UCCR/images/paste-group.png"  alt="붙여넣기 아이콘">을 클릭하십시오. 

그룹을 잘라내려면 그룹을 선택하고 **잘라내기** 아이콘 <img class="inline" src="../UCCR/images/cut-group.png"  alt="잘라내기 아이콘">을 클릭하십시오. 

그룹을 그룹화 해제하려면 그룹을 선택하고 그룹 선택 표시줄에서 **그룹화 해제** 아이콘 <img class="inline" src="../UCCR/images/ungroup-icon.png"  alt="그룹화 해제 아이콘">을 클릭하십시오. 

그룹에 있는 태스크를 삭제하려면 그룹을 선택하고 **삭제** 아이콘 <img class="inline" src="../UCCR/images/trash-group.png"  alt="삭제 아이콘">을 클릭하십시오. 태스크가 배치 플랜에서 제거됩니다. 

## 태스크 태그 관리
{: #tasks_tags}

태그는 사용자가 태스크에 추가할 수 있는 구성 요소입니다. 태그로 배치 플랜을 필터링할 수 있습니다. 예를 들어, 프로덕션 환경에 배치하는 중에 태스크가 개발 환경 전용임을 표시하는 `DEV_only` 태그가 포함된 태스크를 사용하지 않을 수 있습니다. 

태스크에 태그를 추가하려면 다음 단계를 따르십시오. 

1. 배치 플랜 세부사항 페이지에서 태스크 또는 태스크 그룹을 선택하고 **태그 관리** <img class="inline" src="../UCCR/images/task-tag.png"  alt="태그 관리">를 클릭하십시오. 여러 개의 태스크와 그룹을 선택할 수 있습니다. 

1. "선택된 태스크의 태그 관리" 창의 **공통 태그** 목록에서 태그를 선택하십시오. 목록의 텍스트 상자에서 이름을 입력하여 태그를 작성할 수 있습니다. 

1. **저장**을 클릭하십시오.

태그가 배치 플랜 세부사항 페이지의 태스크 행에 표시됩니다. 다음 그림에서 WAR 배치 태스크에는 두 개의 태그(`Deployment` 및 `Critical`)가 있습니다. 

배치 플랜에서 사용하는 태그는 배치 플랜 세부사항의 **버전** 탭에 표시됩니다. 배치에 적용할 수 없도록 태스크를 렌더링하려면 태스크의 태그를 지우십시오. "적용할 수 없음" 상태의 태스크는 시작될 수 없습니다.   

![](../UCCR/images/task-tag-labels.png "일반 배치 플랜")

*그림 3. 태스크 태그*

## 태스크 종속 항목 작성
{: #tasks_dependencies}

태스크를 기타 태스크의 전제조건으로 지정할 수 있습니다. 태스크가 전제조건인 경우에는 종속자 태스크가 자격을 갖추어도 전제조건 태스크가 종료될 때까지 이를 시작할 수 없습니다. 

태스크에는 여러 개의 종속자 태스크와 여러 개의 전제조건 태스크가 있을 수 있습니다. 사용자는 배치 플랜의 기타 태스크에서 태스크의 종속 항목을 정의할 수 있습니다. 그러나 순환 종속성을 작성할 수는 없습니다. 예를 들어, 자신이 첫 번째 태스크에 종속되는 태스크에는 태스크를 종속시킬 수 없습니다. 

사용자는 태스크 종속 항목을 제어하여 이벤트가 예상되는 순서대로 발생하도록 보장할 수 있습니다. 

태스크를 기타 태스크의 전제조건으로 지정하려면 다음 단계를 완료하십시오. 

1. 배치 플랜 세부사항 페이지에서 태스크 또는 태스크 그룹을 선택하고 **전제조건 관리** <img class="inline" src="../UCCR/images/task-depend.png"  alt="태스크 전제조건">을 클릭하십시오. 여러 개의 태스크와 그룹을 선택할 수 있습니다. 

1. "선택된 태스크의 전제조건 관리" 창의 **선택된 태스크의 전제조건 태스크** 목록에서 전제조건 태스크를 선택하십시오. 

1. **저장**을 클릭하십시오.

태스크 종속 항목이 배치 플랜 세부사항 페이지의 종속 항목 열에 표시됩니다. 위로 화살표는 태스크 전제조건을 표시하며 아래로 화살표는 태스크 종속 항목을 표시합니다. 

다음 그림에서 첫 번째 태스크에는 전제조건이 없으며 두 개의 태스크가 이에 종속됩니다. 두 번째 태스크에는 하나의 전제조건 태스크가 있으며 이에 종속된 태스크는 없습니다. 

(![](../UCCR/images/plan-w-depend.png "일반 배치 플랜"))

*그림 4. 태스크 종속 항목*

종속 항목을 검토하거나 수정하려면 태스크를 선택하고 **전제조건 관리** <img class="inline" src="../UCCR/images/task-depend.png"  alt="태스크 전제조건">을 클릭하십시오. 