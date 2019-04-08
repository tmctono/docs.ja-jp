---
title: CorDeclSecurity 列挙型
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5409d1b89ba3e50c4ae17ed5aa6bf063cf6c93cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136969"
---
# <a name="cordeclsecurity-enumeration"></a><span data-ttu-id="1d242-102">CorDeclSecurity 列挙型</span><span class="sxs-lookup"><span data-stu-id="1d242-102">CorDeclSecurity Enumeration</span></span>
<span data-ttu-id="1d242-103">宣言型セキュリティを使用して実行できるセキュリティ アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d242-103">Specifies the security actions that can be performed using declarative security.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d242-104">構文</span><span class="sxs-lookup"><span data-stu-id="1d242-104">Syntax</span></span>  
  
```  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a><span data-ttu-id="1d242-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="1d242-105">Members</span></span>  
  
|<span data-ttu-id="1d242-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="1d242-106">Member</span></span>|<span data-ttu-id="1d242-107">説明</span><span class="sxs-lookup"><span data-stu-id="1d242-107">Description</span></span>|  
|------------|-----------------|  
|`dclActionMask`|<span data-ttu-id="1d242-108">予約済み。</span><span class="sxs-lookup"><span data-stu-id="1d242-108">Reserved.</span></span>|  
|`dclActionNil`|<span data-ttu-id="1d242-109">予約済み。</span><span class="sxs-lookup"><span data-stu-id="1d242-109">Reserved.</span></span>|  
|`dclRequest`|<span data-ttu-id="1d242-110">予約済み。</span><span class="sxs-lookup"><span data-stu-id="1d242-110">Reserved.</span></span>|  
|`dclDemand`|<span data-ttu-id="1d242-111">呼び出し履歴の上位にあるすべての呼び出し元には、現在のアクセス許可オブジェクトで指定されたアクセス許可が付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d242-111">All callers higher in the call stack are required to have been granted the permission specified by the current permission object.</span></span>|  
|`dclAssert`|<span data-ttu-id="1d242-112">呼び出し元のコードは、リソースにアクセスするためのアクセス許可が呼び出し元のスタックの上位に与えられていない場合でも、現在のアクセス許可オブジェクトで識別されるリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1d242-112">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span></span>|  
|`dclDeny`|<span data-ttu-id="1d242-113">アクセス許可を付与されている場合でも、呼び出し元に対して、現在のアクセス許可オブジェクトによって指定されるリソースにアクセスする権限が拒否されました。</span><span class="sxs-lookup"><span data-stu-id="1d242-113">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span></span>|  
|`dclPermitOnly`|<span data-ttu-id="1d242-114">他のリソースにアクセスできるアクセス許可がコードに付与されていても、このアクセス許可オブジェクトで指定されたリソースにしかアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="1d242-114">Only the resources specified by this permission object can be accessed, even if the code has been granted permission to access other resources.</span></span>|  
|`dclLinktimeCheck`|<span data-ttu-id="1d242-115">直前の呼び出し元は、一定の期間の指定した権限が付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d242-115">The immediate caller is required to have been granted the specified permission for a given period of time.</span></span>|  
|`dclInheritanceCheck`|<span data-ttu-id="1d242-116">別のクラスを継承またはメソッドをオーバーライドする派生クラスは、指定した権限が付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d242-116">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span></span>|  
|`dclRequestMinimum`|<span data-ttu-id="1d242-117">呼び出し元は、コードを実行するために必要な最小限のアクセス許可を要求できます。</span><span class="sxs-lookup"><span data-stu-id="1d242-117">The caller can request for the minimum permissions required for code to run.</span></span> <span data-ttu-id="1d242-118">この操作は、アセンブリのスコープ内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d242-118">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestOptional`|<span data-ttu-id="1d242-119">呼び出し元は、追加は省略可能です (実行には必要ありません) のアクセス許可を要求できます。</span><span class="sxs-lookup"><span data-stu-id="1d242-119">The caller can request for additional permissions that are optional (not required to run).</span></span> <span data-ttu-id="1d242-120">この要求は、個別に要求されていない、他のすべてのアクセス許可を暗黙的に拒否します。</span><span class="sxs-lookup"><span data-stu-id="1d242-120">This request implicitly refuses all other permissions not specifically requested.</span></span> <span data-ttu-id="1d242-121">この操作は、アセンブリのスコープ内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d242-121">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestRefuse`|<span data-ttu-id="1d242-122">呼び出し元の要求が悪用された場合のアクセス許可は付与されません。</span><span class="sxs-lookup"><span data-stu-id="1d242-122">The caller's request for permissions that might be misused will not be granted.</span></span> <span data-ttu-id="1d242-123">この操作は、アセンブリのスコープ内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d242-123">This action can only be used within the scope of the assembly.</span></span>|  
|`dclPrejitGrant`|<span data-ttu-id="1d242-124">予約済み。</span><span class="sxs-lookup"><span data-stu-id="1d242-124">Reserved.</span></span>|  
|`dclPrejitDenied`|<span data-ttu-id="1d242-125">予約済み。</span><span class="sxs-lookup"><span data-stu-id="1d242-125">Reserved.</span></span>|  
|`dclNonCasDemand`|<span data-ttu-id="1d242-126">予約済み。</span><span class="sxs-lookup"><span data-stu-id="1d242-126">Reserved.</span></span>|  
|`dclNonCasLinkDemand`|<span data-ttu-id="1d242-127">直接の呼び出し元には、指定したアクセス許可が付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d242-127">The immediate caller is required to have been granted the specified permission.</span></span>|  
|`dclNonCasInheritance`|<span data-ttu-id="1d242-128">予約済み。</span><span class="sxs-lookup"><span data-stu-id="1d242-128">Reserved.</span></span>|  
|`dclLinkDemandChoice`|<span data-ttu-id="1d242-129">予約済み。</span><span class="sxs-lookup"><span data-stu-id="1d242-129">Reserved.</span></span>|  
|`dclInheritanceDemandChoice`|<span data-ttu-id="1d242-130">予約済み。</span><span class="sxs-lookup"><span data-stu-id="1d242-130">Reserved.</span></span>|  
|`dclDemandChoice`|<span data-ttu-id="1d242-131">予約済み。</span><span class="sxs-lookup"><span data-stu-id="1d242-131">Reserved.</span></span>|  
|`dclMaximumValue`|<span data-ttu-id="1d242-132">予約済み。</span><span class="sxs-lookup"><span data-stu-id="1d242-132">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d242-133">必要条件</span><span class="sxs-lookup"><span data-stu-id="1d242-133">Requirements</span></span>  
 <span data-ttu-id="1d242-134">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d242-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d242-135">**ヘッダー:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="1d242-135">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="1d242-136">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="1d242-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1d242-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d242-137">See also</span></span>

- [<span data-ttu-id="1d242-138">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="1d242-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
