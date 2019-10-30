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
ms.openlocfilehash: 4dc91723f009d46f9c57b1c99aa66ba7a1b127e4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126631"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="f676c-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList メソッド</span><span class="sxs-lookup"><span data-stu-id="f676c-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="f676c-103">指定された名前がリスト内のアセンブリの名前と一致するかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f676c-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f676c-104">構文</span><span class="sxs-lookup"><span data-stu-id="f676c-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f676c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f676c-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="f676c-106">から検索対象のアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="f676c-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f676c-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="f676c-107">Return Value</span></span>  
  
|<span data-ttu-id="f676c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f676c-108">HRESULT</span></span>|<span data-ttu-id="f676c-109">説明</span><span class="sxs-lookup"><span data-stu-id="f676c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f676c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f676c-110">S_OK</span></span>|<span data-ttu-id="f676c-111">文字列が一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f676c-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="f676c-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f676c-112">S_FALSE</span></span>|<span data-ttu-id="f676c-113">文字列は一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="f676c-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="f676c-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f676c-114">E_FAIL</span></span>|<span data-ttu-id="f676c-115">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="f676c-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f676c-116">メソッドから E_FAIL が返された後は、共通言語ランタイムをプロセス内で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f676c-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="f676c-117">後続のホストメソッドの呼び出しでは、HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="f676c-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f676c-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="f676c-118">Requirements</span></span>  
 <span data-ttu-id="f676c-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f676c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f676c-120">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f676c-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f676c-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f676c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f676c-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f676c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f676c-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="f676c-123">See also</span></span>

- [<span data-ttu-id="f676c-124">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f676c-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="f676c-125">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f676c-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="f676c-126">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f676c-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="f676c-127">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f676c-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
