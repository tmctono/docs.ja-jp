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
ms.openlocfilehash: e3e50538bde8fe3509b49e3dbcb031875e6863e5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127118"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="34189-102">IAssemblyCache::CreateAssemblyCacheItem メソッド</span><span class="sxs-lookup"><span data-stu-id="34189-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="34189-103">新しい[Iassemblycacheitem](iassemblycacheitem-interface.md)オブジェクトへの参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="34189-103">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34189-104">構文</span><span class="sxs-lookup"><span data-stu-id="34189-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34189-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34189-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="34189-106">からFusion に定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="34189-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="34189-107">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="34189-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="34189-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="34189-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="34189-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="34189-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="34189-110">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="34189-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="34189-111">`pvReserved` は null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="34189-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="34189-112">入出力返された `IAssemblyCacheItem` ポインター。</span><span class="sxs-lookup"><span data-stu-id="34189-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="34189-113">[in、optional]正規化が解除、コンマ区切りの `name=value` ペア。</span><span class="sxs-lookup"><span data-stu-id="34189-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34189-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="34189-114">Requirements</span></span>  
 <span data-ttu-id="34189-115">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34189-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34189-116">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="34189-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="34189-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34189-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34189-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="34189-118">See also</span></span>

- [<span data-ttu-id="34189-119">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34189-119">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="34189-120">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="34189-120">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
