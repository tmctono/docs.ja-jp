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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffeb04ddcec290f899556bf0d8078acfb06707ac
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778607"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="55734-102">CreateAssemblyCache 関数</span><span class="sxs-lookup"><span data-stu-id="55734-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="55734-103">新しいポインターを取得します。 [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)グローバル アセンブリ キャッシュを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="55734-103">Gets a pointer to a new [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55734-104">構文</span><span class="sxs-lookup"><span data-stu-id="55734-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="55734-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="55734-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="55734-106">[out]返された`IAssemblyCache`ポインター。</span><span class="sxs-lookup"><span data-stu-id="55734-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="55734-107">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="55734-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="55734-108">`dwReserved` 0 (ゼロ) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="55734-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55734-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="55734-109">Requirements</span></span>  
 <span data-ttu-id="55734-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55734-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55734-111">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="55734-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="55734-112">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="55734-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="55734-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55734-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55734-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="55734-114">See also</span></span>

- [<span data-ttu-id="55734-115">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55734-115">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="55734-116">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="55734-116">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="55734-117">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="55734-117">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
