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
ms.openlocfilehash: 0632a7f5feee87c386d9488a6c989413af68a47f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615892"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="96f21-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList メソッド</span><span class="sxs-lookup"><span data-stu-id="96f21-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="96f21-103">指定されたポインターがリスト内のアセンブリを参照しているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="96f21-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96f21-104">構文</span><span class="sxs-lookup"><span data-stu-id="96f21-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96f21-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="96f21-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="96f21-106">から検索対象のアセンブリへのインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="96f21-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="96f21-107">有効な値は `IAssemblyName` 、型または型です `IReferenceIdentity` 。</span><span class="sxs-lookup"><span data-stu-id="96f21-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96f21-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="96f21-108">Return Value</span></span>  
  
|<span data-ttu-id="96f21-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="96f21-109">HRESULT</span></span>|<span data-ttu-id="96f21-110">説明</span><span class="sxs-lookup"><span data-stu-id="96f21-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="96f21-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="96f21-111">S_OK</span></span>|<span data-ttu-id="96f21-112">文字列が一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="96f21-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="96f21-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="96f21-113">S_FALSE</span></span>|<span data-ttu-id="96f21-114">文字列は一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="96f21-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="96f21-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="96f21-115">E_FAIL</span></span>|<span data-ttu-id="96f21-116">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="96f21-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="96f21-117">メソッドが E_FAIL を返すと、そのプロセス内で共通言語ランタイムは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="96f21-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="96f21-118">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="96f21-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="96f21-119">要件</span><span class="sxs-lookup"><span data-stu-id="96f21-119">Requirements</span></span>  
 <span data-ttu-id="96f21-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96f21-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96f21-121">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="96f21-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96f21-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="96f21-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96f21-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96f21-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96f21-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="96f21-124">See also</span></span>

- [<span data-ttu-id="96f21-125">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96f21-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="96f21-126">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96f21-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="96f21-127">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96f21-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="96f21-128">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96f21-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
