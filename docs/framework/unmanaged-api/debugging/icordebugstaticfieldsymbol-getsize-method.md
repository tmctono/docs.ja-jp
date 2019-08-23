---
title: ICorDebugStaticFieldSymbol::GetSize メソッド
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d99e06c1093dbc67e9c1999e4b9ccabd6579340e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962660"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="8346e-102">ICorDebugStaticFieldSymbol::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="8346e-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="8346e-103">静的フィールドのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="8346e-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8346e-104">構文</span><span class="sxs-lookup"><span data-stu-id="8346e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8346e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8346e-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="8346e-106">[out] フィールドの長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8346e-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8346e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8346e-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8346e-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8346e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8346e-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="8346e-109">Requirements</span></span>  
 <span data-ttu-id="8346e-110">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8346e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8346e-111">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8346e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8346e-112">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="8346e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8346e-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8346e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8346e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="8346e-114">See also</span></span>

- [<span data-ttu-id="8346e-115">ICorDebugStaticFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8346e-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="8346e-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8346e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
