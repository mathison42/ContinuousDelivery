---

copyright:
  years: 2016, 2018
lastupdated: "2018-8-2"
---
<!-- Copyright info at top of file: REQUIRED
    The copyright info is YAML content that must occur at the top of the MD file, before attributes are listed.
    It must be surrounded by 3 dashes.
    The value "years" can contain just one year or a two years separated by a comma. (years: 2014, 2016)
    Indentation as per the previous template must be preserved.
-->

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 빌드 및 배치
{: #deliverypipeline_build_deploy}

{{site.data.keyword.contdelivery_full}}에는 반복 가능한 지속적 통합 및 지속적 딜리버리 프로세스를 구현할 수 있는 Delivery Pipeline이 포함됩니다.
{:shortdesc}

파이프라인을 구성하려면 다음 태스크를 완료하십시오.

## 단계 추가
{: #deliverypipeline_add_stage}

1. 파이프라인 페이지에서 **단계 추가**를 클릭하십시오. 단계 구성 페이지가 열립니다.
2. 단계를 구성하십시오.
  1. **입력** 탭에서 단계의 입력을 선택하십시오.  빌드 단계의 경우 입력 탭에는 저장소에 입력으로 사용할 분기를 지정하는 **분기** 필드가 포함되어 있습니다.
  2. **작업** 탭에서 하나 이상의 작업을 추가하고 구성하십시오. 첫 번째 단계에는 주로 하나 이상의 빌드 작업이 있습니다.
3. **저장**을 클릭하십시오.

## 단계에 작업 추가
{: #deliverypipeline_add_job}

1. 단계에서 **단계 구성** 아이콘을 클릭한 후 **단계 구성**를 클릭하십시오.
2. **작업** 탭을 클릭하십시오.
3. **작업 추가**를 클릭하십시오. 추가할 작업의 유형을 선택하십시오.
4. 작업을 구성하십시오.
5. **저장**을 클릭하십시오.

![단계에 작업 추가](images/AddJob2.png)

## 단계 실행
{: #deliverypipeline_run_stage}

파이프라인 페이지에서 **단계 실행** 아이콘을 클릭하여 단계를 수동으로 실행할 수 있습니다.

![작업의 실행 단계 아이콘 클릭](images/RunStage.png)

다음 두 방법 중 하나로 빌드 히스토리 페이지에서 On-Demand 빌드 및 배치를 요청할 수도 있습니다.
* 구성된 단계 아래에 있는 상자로 빌드를 끌어옵니다.
* LAST EXECUTION RESULT 섹션에서 **전송 대상** 아이콘을 클릭한 후 배치할 영역을 선택하십시오.
![이 빌드 아이콘을 사용한 실행 단계](images/deploy_to.png)

실행 중인 단계를 취소하려면 단계에서 **로그 및 히스토리 보기**를 클릭하십시오. 작업 목록에서 실행 작업의 번호를 클릭한 후 **취소**를 클릭하십시오. 작업을 클릭한 후 **취소**를 클릭하거나 해당 단계에서 작업에 대해 **중지** 아이콘을 클릭하여 작업을 개별적으로 취소할 수도 있습니다.

## 앱 배치
{: #deliverypipeline_deploy}

적절히 구성된 배치 작업은 실행될 때마다 대상에 앱을 배치합니다. 배치 작업을 수동으로 실행하려면 작업이 있는 단계의 **단계 실행** 아이콘을 클릭하십시오.

###입력 변경내용
단계를 수동으로 실행하거나 이전 단계가 완료되었기 때문에 단계가 실행되는 경우, 실행 단계는 해당 입력 변경내용을 선택합니다. 주로 입력 변경내용은 빌드 번호입니다. 입력 변경내용을 선택하기 위해 단계에서 다음 조건을 따릅니다.

* 특정 변경내용이 선택되어 있으면 이를 사용합니다.
* 특정 변경내용이 지정되어 있지 않으면 동일한 입력을 사용하는 단계를 찾을 때까지 이전 단계를 검색합니다. 성공적으로 실행된 해당 입력의 마지막 변경내용을 찾아 이를 사용합니다.
* 특정 변경내용이 지정되어 있지 않고 지정된 소스를 입력으로 사용하는 다른 단계가 없으면 입력의 최신 변경내용을 사용합니다.

이전 빌드를 배치할 수 있습니다. 빌드가 포함된 단계에서 **로그 및 히스토리 보기**를 클릭하십시오. 열린 페이지에서 클릭하여 실행 번호를 펼친 후 빌드 작업을 클릭하십시오. **받는 사람**을 클릭하고 대상을 선택하십시오.
{: tip}

###앱에 서비스 추가
앱에 서비스를 추가하고 {{site.data.keyword.Bluemix_notm}} 대시보드 또는 Cloud Foundry CLI(Command Line Interface)에서 이러한 서비스를 관리할 수 있습니다. 또한 파이프라인 작업에 대해 스크립트에서 Cloud Foundry CLI 명령을 실행할 수도 있습니다. 예를 들어, 배치 작업의 스크립트에서 앱에 서비스를 추가할 수 있습니다. 서비스 추가에 대한 자세한 정보는 [애플리케이션에 서비스 추가](/docs/services/reqnsi.html#add_service)를 참조하십시오.

## 로그 보기
{: #deliverypipeline_view_logs}

단계 히스토리 페이지에서 작업에 대한 로그와 단계를 실행되는 대로 볼 수 있습니다.

작업의 로그를 보려면 작업을 클릭하십시오. 또는 단계에서 **로그 및 히스토리 보기**를 클릭하십시오.

배치된 애플리케이션의 런타임 로그를 보려면 **런타임 로그 보기**를 클릭하십시오.

![클릭하여 관련 로그를 열 수 있는 단계 타일의 영역](images/view_logs_and_history.png)

작업 로그 이외에, 단위 테스트 결과, 생성된 아티팩트 및 빌드 작업의 코드 변경사항을 볼 수 있습니다.

또한 단계 히스토리 페이지에서 단계를 실행, 재배치, 취소 또는 구성할 수 있습니다. 단계를 실행하려면 **실행**을 클릭하고, 배치 작업인 경우 재배치하려면 **재배치**를 클릭하며 단계를 구성하려는 경우 **구성**을 클릭하십시오. 단계가 실행 중인 동안 실행 번호를 클릭한 후 **취소**를 클릭하여 단계를 취소할 수 있습니다.
