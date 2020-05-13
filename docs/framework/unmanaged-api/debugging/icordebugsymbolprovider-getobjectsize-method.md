---
title: ICorDebugSymbolProvider::GetObjectSize メソッド
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: 64324df49ad0b5dfa3c25455950bddc3d687b178
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379555"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="35d82-102">ICorDebugSymbolProvider::GetObjectSize メソッド</span><span class="sxs-lookup"><span data-stu-id="35d82-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="35d82-103">typespec シグネチャに基づいてオブジェクトのオブジェクト サイズを返します。</span><span class="sxs-lookup"><span data-stu-id="35d82-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35d82-104">構文</span><span class="sxs-lookup"><span data-stu-id="35d82-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35d82-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="35d82-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="35d82-106">[in] typespec シグネチャのバイト数。</span><span class="sxs-lookup"><span data-stu-id="35d82-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="35d82-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="35d82-107">typeSig</span></span>  
 <span data-ttu-id="35d82-108">[in] typespec シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="35d82-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="35d82-109">[out] オブジェクトのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="35d82-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35d82-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="35d82-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35d82-111">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="35d82-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35d82-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="35d82-112">Requirements</span></span>  
 <span data-ttu-id="35d82-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35d82-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35d82-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35d82-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35d82-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35d82-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35d82-116">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35d82-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d82-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="35d82-117">See also</span></span>

- [<span data-ttu-id="35d82-118">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35d82-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="35d82-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="35d82-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
