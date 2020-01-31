---
title: ICorDebugSymbolProvider::GetObjectSize メソッド
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: fce7410b5ae9571af0c8a5963596e2af41737798
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791563"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="6bb85-102">ICorDebugSymbolProvider::GetObjectSize メソッド</span><span class="sxs-lookup"><span data-stu-id="6bb85-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="6bb85-103">typespec シグネチャに基づいてオブジェクトのオブジェクト サイズを返します。</span><span class="sxs-lookup"><span data-stu-id="6bb85-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bb85-104">構文</span><span class="sxs-lookup"><span data-stu-id="6bb85-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bb85-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6bb85-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="6bb85-106">[in] typespec シグネチャのバイト数。</span><span class="sxs-lookup"><span data-stu-id="6bb85-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="6bb85-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="6bb85-107">typeSig</span></span>  
 <span data-ttu-id="6bb85-108">[in] typespec シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="6bb85-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="6bb85-109">[out] オブジェクトのサイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6bb85-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bb85-110">コメント</span><span class="sxs-lookup"><span data-stu-id="6bb85-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6bb85-111">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6bb85-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bb85-112">要件</span><span class="sxs-lookup"><span data-stu-id="6bb85-112">Requirements</span></span>  
 <span data-ttu-id="6bb85-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bb85-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bb85-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6bb85-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6bb85-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bb85-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bb85-116">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bb85-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bb85-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bb85-117">See also</span></span>

- [<span data-ttu-id="6bb85-118">ICorDebugSymbolProvider インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6bb85-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="6bb85-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6bb85-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
