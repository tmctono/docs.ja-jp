---
title: ICorDebugStaticFieldSymbol::GetSize メソッド
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: e36c94bf411e75f915cca86aee74cdf161674d25
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379410"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="dd67b-102">ICorDebugStaticFieldSymbol::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="dd67b-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="dd67b-103">静的フィールドのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="dd67b-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd67b-104">構文</span><span class="sxs-lookup"><span data-stu-id="dd67b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd67b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dd67b-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="dd67b-106">[out] フィールドの長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="dd67b-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd67b-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="dd67b-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd67b-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd67b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd67b-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="dd67b-109">Requirements</span></span>  
 <span data-ttu-id="dd67b-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd67b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd67b-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd67b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd67b-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd67b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd67b-113">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd67b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd67b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd67b-114">See also</span></span>

- [<span data-ttu-id="dd67b-115">ICorDebugStaticFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd67b-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="dd67b-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="dd67b-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
