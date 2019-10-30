---
title: ICLRAssemblyReferenceList::IsAssemblyReferenceInList メソッド
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList method [.NET Framework hosting]
- IsAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: 8a570813-21be-407e-92a6-7ae8de3bc728
topic_type:
- apiref
ms.openlocfilehash: 4e75b8553ff33946654a6a3b6184f98049c6a6cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126680"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="a606a-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList メソッド</span><span class="sxs-lookup"><span data-stu-id="a606a-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="a606a-103">指定されたポインターがリスト内のアセンブリを参照しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="a606a-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a606a-104">構文</span><span class="sxs-lookup"><span data-stu-id="a606a-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a606a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a606a-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="a606a-106">から検索対象のアセンブリへのインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="a606a-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="a606a-107">有効な値は `IAssemblyName` または `IReferenceIdentity`型です。</span><span class="sxs-lookup"><span data-stu-id="a606a-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a606a-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="a606a-108">Return Value</span></span>  
  
|<span data-ttu-id="a606a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a606a-109">HRESULT</span></span>|<span data-ttu-id="a606a-110">説明</span><span class="sxs-lookup"><span data-stu-id="a606a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a606a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a606a-111">S_OK</span></span>|<span data-ttu-id="a606a-112">文字列が一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a606a-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="a606a-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a606a-113">S_FALSE</span></span>|<span data-ttu-id="a606a-114">文字列は一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="a606a-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="a606a-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a606a-115">E_FAIL</span></span>|<span data-ttu-id="a606a-116">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a606a-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a606a-117">メソッドから E_FAIL が返された後は、共通言語ランタイムをプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a606a-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="a606a-118">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="a606a-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a606a-119">［要件］</span><span class="sxs-lookup"><span data-stu-id="a606a-119">Requirements</span></span>  
 <span data-ttu-id="a606a-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a606a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a606a-121">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a606a-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a606a-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a606a-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a606a-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a606a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a606a-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="a606a-124">See also</span></span>

- [<span data-ttu-id="a606a-125">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a606a-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a606a-126">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a606a-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="a606a-127">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a606a-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="a606a-128">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a606a-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
