---
title: IAssemblyCache::CreateAssemblyCacheItem メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4432b17e5d9aa875d8346b3329cd618e15222040
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771019"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="eaab2-102">IAssemblyCache::CreateAssemblyCacheItem メソッド</span><span class="sxs-lookup"><span data-stu-id="eaab2-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="eaab2-103">新しいへの参照を取得します。 [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="eaab2-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaab2-104">構文</span><span class="sxs-lookup"><span data-stu-id="eaab2-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaab2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eaab2-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="eaab2-106">[in]ものがありますで定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="eaab2-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="eaab2-107">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="eaab2-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="eaab2-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="eaab2-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="eaab2-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="eaab2-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="eaab2-110">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="eaab2-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="eaab2-111">`pvReserved` null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaab2-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="eaab2-112">[out]返された`IAssemblyCacheItem`ポインター。</span><span class="sxs-lookup"><span data-stu-id="eaab2-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="eaab2-113">[in、省略可能]Uncanonicalized、コンマで区切られた`name=value`ペア。</span><span class="sxs-lookup"><span data-stu-id="eaab2-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaab2-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="eaab2-114">Requirements</span></span>  
 <span data-ttu-id="eaab2-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaab2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaab2-116">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="eaab2-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="eaab2-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaab2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaab2-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaab2-118">See also</span></span>

- [<span data-ttu-id="eaab2-119">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eaab2-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="eaab2-120">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eaab2-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
