---

copyright:

  years: 2015, 2018
lastupdated: "2018-01-26"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# API 키 작업
{: #manapikey}

API(Application Programming Interface) 키는 호출 애플리케이션 또는 사용자를 식별하도록 API(Application Programming Interface)에 전달되는 고유 코드입니다.  API 키를 사용하여 API의 사용을 추적 및 제어할 수 있습니다. 예를 들어, 악의적 사용 또는 남용을 방지하는 데 이 API 키를 사용할 수 있습니다. API 키는 종종 인증을 위한 시크릿 토큰 및 고유 ID 모두의 역할을 하며, 일반적으로 이와 연관된 ID에 대한 액세스 권한 세트를 보유합니다.

## 플랫폼 API 키

플랫폼 API 키는 Identity and Access Management UI에서 작성되며 다음과 연관될 수 있습니다. 

* 계정의 사용자
* 계정에서 작성된 서비스 ID

계정에 링크되는 API 키를 작성하고 사용할 수 있습니다. 연합 또는 비연합 사용자는 CLI에서 또는 자동화의 일부로 사용하여 사용자 ID로 로그인하기 위해 API 키를 작성할 수 있습니다. 사용자 ID와 연관된 API 키 사용에 대한 자세한 정보는 [사용자 API 키 관리](userid_keys.html)를 참조하십시오.

또한 작성하는 서비스 ID와 연관된 API 키를 사용할 수 있습니다. 서비스 ID를 사용하면 {{site.data.keyword.Bluemix_notm}}의 내부나 외부에 있는 애플리케이션을 {{site.data.keyword.Bluemix_notm}} 서비스에 연결할 수 있습니다. 서비스 ID와 연관된 API 키 작성에 대한 자세한 정보는 [서비스 ID API 키 관리](serviceid_keys.html)를 참조하십시오.

## 기타 {{site.data.keyword.Bluemix_notm}} API 키

플랫폼 API 키에 추가하여 {{site.data.keyword.Bluemix_notm}} 사용 중에 사용할 수 있는 몇몇 기타 API 키 유형이 있습니다. 

* 인프라 API 키
* 서비스 특정 API 키

인프라 API 키는 고객 포털에서 작성되고 SoftLayer 계정 사용자 ID와 연관되며 인프라 서비스에 대해 API에 액세스할 때 사용됩니다. 

{{site.data.keyword.Bluemix_notm}}의 일부 서비스는 서비스와 상호작용할 때 사용자가 사용할 API 키를 제공할 수도 있습니다. 예를 들어, 대시보드에서 Watson 서비스의 서비스 세부사항을 보는 경우에는 서비스 신임 정보 탭에서 해당 서비스에만 특정한 API 키 및 시크릿이 포함된 신임 정보를 작성할 수 있습니다. 

