---

copyright:

  years: 2017, 2018

lastupdated: "2017-11-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IAM 및 Cloud Foundry 액세스 모델
{: #accessmodels}

현재 모든 {{site.data.keyword.Bluemix_notm}} 서비스가 Cloud IAM 액세스 관리의 사용을 지원하지는 않습니다. Cloud IAM을 사용할 수 없는 서비스는 여전히 Cloud Foundry 조직 및 영역의 사용자 역할에 의존하여 사용자에게 리소스에 액세스할 권한이 있는지 여부를 판별합니다. {{site.data.keyword.Bluemix_notm}} ID 및 액세스 UI를 사용하면 Cloud IAM 또는 Cloud Foundry 액세스 관리 시스템을 사용하는 서비스에 대한 액세스를 관리할 수 있습니다.


## Cloud Foundry 서비스를 Cloud IAM으로 전환
{: #cftoiam}

Cloud IAM 액세스 관리 사용을 지원하기 시작하는 Cloud Foundry 서비스를 현재 사용 중인 경우에는 작성 중인 새 서비스 인스턴스에 대해 이제 IAM의 액세스 제어를 활용할 수 있다는 알림을 받게 됩니다.

서비스가 Cloud IAM의 사용을 시작하면 다음을 예상할 수 있습니다.

* Cloud Foundry 역할로 조직 및 영역에 사용자를 지정하여 이미 Cloud Foundry 액세스 관리를 사용 중인 계정의 기존 인스턴스의 경우, 변경사항 없이 해당 인스턴스를 계속해서 사용할 수 있습니다.
* 새 인스턴스 작성의 경우, 각각을 계정의 리소스 그룹에 지정한 후에 Cloud IAM을 사용하여 해당 인스턴스 및 이 인스턴스가 속하는 리소스 그룹에 대한 액세스를 관리할 수 있습니다(리소스 그룹에 대한 관리자인 경우).

Cloud IAM 사용을 지원하는 서비스에는 임의의 Cloud Foundry 영역에서 앱과 서비스에 연결하는 기능(이는 서로 다른 지역에서 앱과 서비스에 연결할 수 있도록 허용함)을 포함하여 여러 장점이 있습니다. 또한 Cloud IAM에서 관리하는 각각의 인스턴스는 리소스 그룹에 속합니다. 그리고 리소스 그룹이 지역별 범위가 아니므로, 서로 다른 지역의 앱과 서비스를 동일한 리소스 그룹으로 프로비저닝할 수 있습니다. 또한 개별 인스턴스까지 세분화된 액세스 제어를 사용하기 위한 기능도 있습니다.
