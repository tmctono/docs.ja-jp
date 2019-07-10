---
title: GetAssemblyIdentityFromFile 関数
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 581c675cfb69503e6366471a469ffed1a2d13b1a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745236"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="80a81-102">GetAssemblyIdentityFromFile 関数</span><span class="sxs-lookup"><span data-stu-id="80a81-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="80a81-103">ポインターを取得、 `IUnknown` 、指定したオブジェクト`IID`のアセンブリにある指定したファイル パス。</span><span class="sxs-lookup"><span data-stu-id="80a81-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80a81-104">構文</span><span class="sxs-lookup"><span data-stu-id="80a81-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="80a81-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="80a81-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="80a81-106">[in]要求されたアセンブリへの有効なパス。</span><span class="sxs-lookup"><span data-stu-id="80a81-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="80a81-107">[in]`IID`返すインターフェイスの。</span><span class="sxs-lookup"><span data-stu-id="80a81-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="80a81-108">[out]返されるインターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="80a81-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80a81-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="80a81-109">Requirements</span></span>  
 <span data-ttu-id="80a81-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="80a81-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80a81-111">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="80a81-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="80a81-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80a81-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a81-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="80a81-113">See also</span></span>

- [<span data-ttu-id="80a81-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="80a81-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="80a81-115">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="80a81-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
