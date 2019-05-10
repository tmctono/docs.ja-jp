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
ms.openlocfilehash: a19ea52007edcc1930a2be46059a35b9cbebdc52
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650394"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="38340-102">IAssemblyCache::CreateAssemblyCacheItem メソッド</span><span class="sxs-lookup"><span data-stu-id="38340-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="38340-103">新しいへの参照を取得します。 [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="38340-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38340-104">構文</span><span class="sxs-lookup"><span data-stu-id="38340-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38340-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="38340-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="38340-106">[in]ものがありますで定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="38340-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="38340-107">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="38340-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="38340-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="38340-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="38340-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="38340-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="38340-110">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="38340-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="38340-111">`pvReserved` null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="38340-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="38340-112">[out]返された`IAssemblyCacheItem`ポインター。</span><span class="sxs-lookup"><span data-stu-id="38340-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="38340-113">[in、省略可能]Uncanonicalized、コンマで区切られた`name=value`ペア。</span><span class="sxs-lookup"><span data-stu-id="38340-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38340-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="38340-114">Requirements</span></span>  
 <span data-ttu-id="38340-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38340-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38340-116">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="38340-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="38340-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38340-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38340-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="38340-118">See also</span></span>

- [<span data-ttu-id="38340-119">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38340-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="38340-120">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38340-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
