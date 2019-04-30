---
title: ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList メソッド
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de17a91b5093372579a4d9435532a95406addd0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969911"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="8bb65-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList メソッド</span><span class="sxs-lookup"><span data-stu-id="8bb65-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="8bb65-103">指定された名前が一覧内のアセンブリの名前と一致するかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="8bb65-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bb65-104">構文</span><span class="sxs-lookup"><span data-stu-id="8bb65-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bb65-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8bb65-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="8bb65-106">[in]検索対象のアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="8bb65-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bb65-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="8bb65-107">Return Value</span></span>  
  
|<span data-ttu-id="8bb65-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8bb65-108">HRESULT</span></span>|<span data-ttu-id="8bb65-109">説明</span><span class="sxs-lookup"><span data-stu-id="8bb65-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8bb65-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8bb65-110">S_OK</span></span>|<span data-ttu-id="8bb65-111">文字列は、一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bb65-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="8bb65-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8bb65-112">S_FALSE</span></span>|<span data-ttu-id="8bb65-113">文字列は、一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="8bb65-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="8bb65-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8bb65-114">E_FAIL</span></span>|<span data-ttu-id="8bb65-115">不明な致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8bb65-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8bb65-116">メソッドには、E_FAIL が返された、後に、共通言語ランタイムは、プロセス内で使用可能ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8bb65-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="8bb65-117">メソッドをホストする後続の呼び出しには、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="8bb65-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8bb65-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="8bb65-118">Requirements</span></span>  
 <span data-ttu-id="8bb65-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bb65-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bb65-120">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8bb65-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8bb65-121">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8bb65-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8bb65-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bb65-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bb65-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bb65-123">See also</span></span>

- [<span data-ttu-id="8bb65-124">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bb65-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="8bb65-125">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bb65-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="8bb65-126">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bb65-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="8bb65-127">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bb65-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
