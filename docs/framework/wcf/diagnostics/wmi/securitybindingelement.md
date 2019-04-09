---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: 1d367d0c5d14e6e75539dd2b20cdffcf2b34963d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153856"
---
# <a name="securitybindingelement"></a><span data-ttu-id="206f6-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="206f6-102">SecurityBindingElement</span></span>
<span data-ttu-id="206f6-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="206f6-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="206f6-104">構文</span><span class="sxs-lookup"><span data-stu-id="206f6-104">Syntax</span></span>  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="206f6-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="206f6-105">Methods</span></span>  
 <span data-ttu-id="206f6-106">SecurityBindingElement クラスは、メソッドを一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="206f6-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="206f6-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="206f6-107">Properties</span></span>  
 <span data-ttu-id="206f6-108">SecurityBindingElement クラスには、次のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="206f6-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="206f6-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="206f6-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="206f6-110">データ型: string</span><span class="sxs-lookup"><span data-stu-id="206f6-110">Data type: string</span></span>  
  
 <span data-ttu-id="206f6-111">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="206f6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="206f6-112">バインディングで使用するアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="206f6-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="206f6-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="206f6-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="206f6-114">データ型 : boolean</span><span class="sxs-lookup"><span data-stu-id="206f6-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="206f6-115">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="206f6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="206f6-116">各メッセージにタイムスタンプが含まれるかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="206f6-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="206f6-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="206f6-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="206f6-118">データ型: string</span><span class="sxs-lookup"><span data-stu-id="206f6-118">Data type: string</span></span>  
  
 <span data-ttu-id="206f6-119">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="206f6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="206f6-120">キーの作成に使用されるエントロピのソースです。</span><span class="sxs-lookup"><span data-stu-id="206f6-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="206f6-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="206f6-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="206f6-122">データの種類:LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="206f6-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="206f6-123">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="206f6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="206f6-124">ローカル サービスに対するバインディング固有のセキュリティ プロパティです。</span><span class="sxs-lookup"><span data-stu-id="206f6-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="206f6-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="206f6-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="206f6-126">データ型: string</span><span class="sxs-lookup"><span data-stu-id="206f6-126">Data type: string</span></span>  
  
 <span data-ttu-id="206f6-127">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="206f6-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="206f6-128">メッセージ セキュリティで使用されるバージョンです。</span><span class="sxs-lookup"><span data-stu-id="206f6-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="206f6-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="206f6-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="206f6-130">データ型: string</span><span class="sxs-lookup"><span data-stu-id="206f6-130">Data type: string</span></span>  
  
 <span data-ttu-id="206f6-131">アクセスの種類:読み取り専用</span><span class="sxs-lookup"><span data-stu-id="206f6-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="206f6-132">このバインディングのセキュリティ ヘッダー内の要素の順序です。</span><span class="sxs-lookup"><span data-stu-id="206f6-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="206f6-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="206f6-133">Requirements</span></span>  
  
|<span data-ttu-id="206f6-134">MOF</span><span class="sxs-lookup"><span data-stu-id="206f6-134">MOF</span></span>|<span data-ttu-id="206f6-135">Servicemodel.mof にて宣言済み。</span><span class="sxs-lookup"><span data-stu-id="206f6-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="206f6-136">名前空間</span><span class="sxs-lookup"><span data-stu-id="206f6-136">Namespace</span></span>|<span data-ttu-id="206f6-137">root\ServiceModel で定義</span><span class="sxs-lookup"><span data-stu-id="206f6-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="206f6-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="206f6-138">See also</span></span>

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
