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
ms.openlocfilehash: 50ec5a23db4d2460480bcc3e463ecd88e7470bde
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134532"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="d7e66-102">GetAssemblyIdentityFromFile 関数</span><span class="sxs-lookup"><span data-stu-id="d7e66-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="d7e66-103">指定したファイルパスにあるアセンブリ内の指定した `IID` を持つ `IUnknown` オブジェクトへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="d7e66-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7e66-104">構文</span><span class="sxs-lookup"><span data-stu-id="d7e66-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7e66-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d7e66-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="d7e66-106">から要求されたアセンブリへの有効なパス。</span><span class="sxs-lookup"><span data-stu-id="d7e66-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="d7e66-107">から返されるインターフェイスの `IID`。</span><span class="sxs-lookup"><span data-stu-id="d7e66-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="d7e66-108">入出力返されたインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="d7e66-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7e66-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="d7e66-109">Requirements</span></span>  
 <span data-ttu-id="d7e66-110">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7e66-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7e66-111">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d7e66-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d7e66-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7e66-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e66-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7e66-113">See also</span></span>

- [<span data-ttu-id="d7e66-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="d7e66-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="d7e66-115">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="d7e66-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
