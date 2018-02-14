---

copyright:

  years: 2015, 2018
lastupdated: "2017-08-23"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# API 키 작업
{: #manapikey}

API(Application Programming Interface) 키는 호출 애플리케이션 또는 사용자를 식별하도록 API(Application Programming Interface)에 전달되는 고유 코드입니다.  API 키를 사용하여 API의 사용을 추적 및 제어할 수 있습니다. 예를 들어, 악의적 사용 또는 남용을 방지하는 데 이 API 키를 사용할 수 있습니다. API 키는 종종 인증을 위한 시크릿 토큰 및 고유 ID 모두의 역할을 하며, 일반적으로 이와 연관된 ID에 대한 액세스 권한 세트를 보유합니다.

API 키를 다음과 연관시킬 수 있습니다.

* 사용자
* 서비스 ID

계정에 링크되는 API 키를 작성하고 사용할 수 있습니다. 연합 또는 비연합 사용자는 CLI에서 또는 자동화의 일부로 사용하여 사용자 ID로 로그인하기 위해 API 키를 작성할 수 있습니다. 사용자 ID와 연관된 API 키 사용에 대한 자세한 정보는 [사용자 API 키 관리](userid_keys.html)를 참조하십시오.

또한 작성하는 서비스 ID와 연관된 API 키를 사용할 수 있습니다. 서비스 ID를 사용하면 {{site.data.keyword.Bluemix_notm}}의 내부나 외부에 있는 애플리케이션을 {{site.data.keyword.Bluemix_notm}} 서비스에 연결할 수 있습니다. 서비스 ID와 연관된 API 키 작성에 대한 자세한 정보는 [서비스 ID API 키 관리](serviceid_keys.html)를 참조하십시오.
