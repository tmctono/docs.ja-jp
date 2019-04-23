---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d9563bd3bfe067ad83bfa03e7c6375a9db933f14
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772103"
---
# <a name="servicecredentials"></a><span data-ttu-id="1d675-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="1d675-102">ServiceCredentials</span></span>
<span data-ttu-id="1d675-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="1d675-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d675-104">構文</span><span class="sxs-lookup"><span data-stu-id="1d675-104">Syntax</span></span>  
  
```csharp
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1d675-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="1d675-105">Methods</span></span>  
 <span data-ttu-id="1d675-106">ServiceCredentials クラスで定義されるメソッドはありません。</span><span class="sxs-lookup"><span data-stu-id="1d675-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1d675-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1d675-107">Properties</span></span>  
 <span data-ttu-id="1d675-108">ServiceCredentials クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="1d675-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="1d675-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="1d675-109">ClientCertificate</span></span>  
 <span data-ttu-id="1d675-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="1d675-110">Data type: string</span></span>  
  
 <span data-ttu-id="1d675-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1d675-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1d675-112">このサービスのための、クライアント証明認証および提供設定です。</span><span class="sxs-lookup"><span data-stu-id="1d675-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="1d675-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="1d675-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="1d675-114">データ型: string</span><span class="sxs-lookup"><span data-stu-id="1d675-114">Data type: string</span></span>  
  
 <span data-ttu-id="1d675-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1d675-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1d675-116">このサービスのための、現在発行されているトークンの認証設定です。</span><span class="sxs-lookup"><span data-stu-id="1d675-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="1d675-117">Peer</span><span class="sxs-lookup"><span data-stu-id="1d675-117">Peer</span></span>  
 <span data-ttu-id="1d675-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="1d675-118">Data type: string</span></span>  
  
 <span data-ttu-id="1d675-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1d675-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1d675-120">ピアのトランスポート エンドポイントによって使用される、現在の証明書の認証および提供の設定です。</span><span class="sxs-lookup"><span data-stu-id="1d675-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="1d675-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="1d675-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="1d675-122">データ型: string</span><span class="sxs-lookup"><span data-stu-id="1d675-122">Data type: string</span></span>  
  
 <span data-ttu-id="1d675-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1d675-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1d675-124">現在のセキュリティで保護された通信の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d675-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="1d675-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="1d675-125">ServiceCertificate</span></span>  
 <span data-ttu-id="1d675-126">データ型: string</span><span class="sxs-lookup"><span data-stu-id="1d675-126">Data type: string</span></span>  
  
 <span data-ttu-id="1d675-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1d675-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1d675-128">このサービスに関連付けられている証明書です。</span><span class="sxs-lookup"><span data-stu-id="1d675-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="1d675-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="1d675-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="1d675-130">データ型: string</span><span class="sxs-lookup"><span data-stu-id="1d675-130">Data type: string</span></span>  
  
 <span data-ttu-id="1d675-131">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1d675-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1d675-132">このサービスのユーザー名/パスワードの設定です。</span><span class="sxs-lookup"><span data-stu-id="1d675-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="1d675-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="1d675-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="1d675-134">データ型: string</span><span class="sxs-lookup"><span data-stu-id="1d675-134">Data type: string</span></span>  
  
 <span data-ttu-id="1d675-135">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="1d675-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1d675-136">このサービスの Windows 認証の設定です。</span><span class="sxs-lookup"><span data-stu-id="1d675-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d675-137">必要条件</span><span class="sxs-lookup"><span data-stu-id="1d675-137">Requirements</span></span>  
  
|<span data-ttu-id="1d675-138">MOF</span><span class="sxs-lookup"><span data-stu-id="1d675-138">MOF</span></span>|<span data-ttu-id="1d675-139">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="1d675-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1d675-140">名前空間</span><span class="sxs-lookup"><span data-stu-id="1d675-140">Namespace</span></span>|<span data-ttu-id="1d675-141">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="1d675-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d675-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d675-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>
