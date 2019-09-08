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
ms.openlocfilehash: 2657ac619bb86bc200de9ce229bf82e4339f78d6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796299"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="f07e7-102">GetAssemblyIdentityFromFile 関数</span><span class="sxs-lookup"><span data-stu-id="f07e7-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="f07e7-103">指定したファイルパス`IUnknown`のアセンブリ内で`IID` 、指定したを持つオブジェクトへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="f07e7-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f07e7-104">構文</span><span class="sxs-lookup"><span data-stu-id="f07e7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="f07e7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f07e7-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="f07e7-106">から要求されたアセンブリへの有効なパス。</span><span class="sxs-lookup"><span data-stu-id="f07e7-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="f07e7-107">から返さ`IID`れるインターフェイスの。</span><span class="sxs-lookup"><span data-stu-id="f07e7-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="f07e7-108">入出力返されたインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="f07e7-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f07e7-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="f07e7-109">Requirements</span></span>  
 <span data-ttu-id="f07e7-110">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f07e7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f07e7-111">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="f07e7-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f07e7-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f07e7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f07e7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f07e7-113">See also</span></span>

- [<span data-ttu-id="f07e7-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="f07e7-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="f07e7-115">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="f07e7-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
