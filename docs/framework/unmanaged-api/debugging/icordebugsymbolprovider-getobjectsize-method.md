---
title: ICorDebugSymbolProvider::GetObjectSize メソッド
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b90e2a097e6dfd35b6237808a7b8b47937774b0d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771324"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="8455b-102">ICorDebugSymbolProvider::GetObjectSize メソッド</span><span class="sxs-lookup"><span data-stu-id="8455b-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="8455b-103">typespec シグネチャに基づいてオブジェクトのオブジェクト サイズを返します。</span><span class="sxs-lookup"><span data-stu-id="8455b-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8455b-104">構文</span><span class="sxs-lookup"><span data-stu-id="8455b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8455b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8455b-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="8455b-106">[in] typespec シグネチャのバイト数。</span><span class="sxs-lookup"><span data-stu-id="8455b-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="8455b-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="8455b-107">typeSig</span></span>  
 <span data-ttu-id="8455b-108">[in] typespec シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="8455b-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="8455b-109">[out] オブジェクトのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8455b-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8455b-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="8455b-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8455b-111">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8455b-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8455b-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="8455b-112">Requirements</span></span>  
 <span data-ttu-id="8455b-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8455b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8455b-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8455b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8455b-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8455b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8455b-116">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8455b-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8455b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8455b-117">See also</span></span>

- [<span data-ttu-id="8455b-118">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8455b-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="8455b-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8455b-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
