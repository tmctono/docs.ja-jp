---
title: CreateAssemblyCache 関数
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
ms.openlocfilehash: 5ef100680328e9ad6261bb9188d7509efa9ab479
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108867"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="1aa9d-102">CreateAssemblyCache 関数</span><span class="sxs-lookup"><span data-stu-id="1aa9d-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="1aa9d-103">グローバルアセンブリキャッシュを表す新しい[Iassemblycache](iassemblycache-interface.md)インスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="1aa9d-103">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aa9d-104">構文</span><span class="sxs-lookup"><span data-stu-id="1aa9d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aa9d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1aa9d-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="1aa9d-106">入出力返された `IAssemblyCache` ポインター。</span><span class="sxs-lookup"><span data-stu-id="1aa9d-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="1aa9d-107">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="1aa9d-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="1aa9d-108">`dwReserved` は 0 (ゼロ) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aa9d-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aa9d-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="1aa9d-109">Requirements</span></span>  
 <span data-ttu-id="1aa9d-110">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aa9d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aa9d-111">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="1aa9d-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1aa9d-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="1aa9d-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1aa9d-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aa9d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aa9d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1aa9d-114">See also</span></span>

- [<span data-ttu-id="1aa9d-115">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1aa9d-115">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="1aa9d-116">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="1aa9d-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="1aa9d-117">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="1aa9d-117">Global Assembly Cache</span></span>](../../app-domains/gac.md)
