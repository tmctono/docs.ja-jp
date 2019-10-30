---
title: は、GetSize メソッド
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: 0fa9c519a40624dd8c5471231263d2430738af87
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131765"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="ac197-102">は、GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="ac197-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="ac197-103">静的フィールドのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="ac197-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac197-104">構文</span><span class="sxs-lookup"><span data-stu-id="ac197-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac197-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ac197-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="ac197-106">[out] フィールドの長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ac197-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac197-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="ac197-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ac197-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac197-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac197-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="ac197-109">Requirements</span></span>  
 <span data-ttu-id="ac197-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac197-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac197-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac197-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac197-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac197-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac197-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac197-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac197-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac197-114">See also</span></span>

- [<span data-ttu-id="ac197-115">ICorDebugStaticFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ac197-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="ac197-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ac197-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
