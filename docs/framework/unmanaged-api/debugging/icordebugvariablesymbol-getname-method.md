---
title: 'ICorDebugVariableSymbol:: GetName メソッド'
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: 9bc32d3372710b4c4e92aa89df5e6e7839ad3078
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121015"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="30885-102">ICorDebugVariableSymbol:: GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="30885-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="30885-103">変数の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="30885-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30885-104">構文</span><span class="sxs-lookup"><span data-stu-id="30885-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30885-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="30885-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="30885-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="30885-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="30885-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="30885-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="30885-108">変数名が格納されている文字配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="30885-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30885-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="30885-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30885-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="30885-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30885-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="30885-111">Requirements</span></span>  
 <span data-ttu-id="30885-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30885-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30885-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30885-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30885-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30885-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30885-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30885-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30885-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="30885-116">See also</span></span>

- [<span data-ttu-id="30885-117">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="30885-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="30885-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="30885-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
