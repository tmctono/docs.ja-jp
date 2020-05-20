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
ms.openlocfilehash: 91f174cab4986882df795eb531baedfc0dd43962
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615866"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="b6c29-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList メソッド</span><span class="sxs-lookup"><span data-stu-id="b6c29-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="b6c29-103">指定された名前がリスト内のアセンブリの名前と一致するかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="b6c29-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6c29-104">構文</span><span class="sxs-lookup"><span data-stu-id="b6c29-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6c29-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b6c29-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="b6c29-106">から検索対象のアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="b6c29-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6c29-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="b6c29-107">Return Value</span></span>  
  
|<span data-ttu-id="b6c29-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b6c29-108">HRESULT</span></span>|<span data-ttu-id="b6c29-109">説明</span><span class="sxs-lookup"><span data-stu-id="b6c29-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6c29-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6c29-110">S_OK</span></span>|<span data-ttu-id="b6c29-111">文字列が一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6c29-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="b6c29-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b6c29-112">S_FALSE</span></span>|<span data-ttu-id="b6c29-113">文字列は一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="b6c29-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="b6c29-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b6c29-114">E_FAIL</span></span>|<span data-ttu-id="b6c29-115">原因不明の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b6c29-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b6c29-116">メソッドが E_FAIL を返すと、そのプロセス内で共通言語ランタイムは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b6c29-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="b6c29-117">後続のホストメソッドの呼び出しでは HOST_E_CLRNOTAVAILABLE が返されます。</span><span class="sxs-lookup"><span data-stu-id="b6c29-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6c29-118">要件</span><span class="sxs-lookup"><span data-stu-id="b6c29-118">Requirements</span></span>  
 <span data-ttu-id="b6c29-119">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6c29-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6c29-120">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b6c29-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b6c29-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b6c29-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6c29-122">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6c29-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c29-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6c29-123">See also</span></span>

- [<span data-ttu-id="b6c29-124">ICLRAssemblyIdentityManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6c29-124">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="b6c29-125">ICLRAssemblyReferenceList インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6c29-125">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="b6c29-126">IHostAssemblyManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6c29-126">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="b6c29-127">IHostAssemblyStore インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b6c29-127">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
