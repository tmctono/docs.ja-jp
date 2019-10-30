---
title: の場合は、次のようにします。、GetName メソッド
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: d88e18b8d6d497098e340b396972f9ead28dbaf6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139054"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="298f6-102">の場合は、次のようにします。、GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="298f6-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="298f6-103">インスタンス フィールドの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="298f6-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="298f6-104">構文</span><span class="sxs-lookup"><span data-stu-id="298f6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="298f6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="298f6-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="298f6-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="298f6-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="298f6-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="298f6-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="298f6-108">[out] 返される名前を格納する文字配列。</span><span class="sxs-lookup"><span data-stu-id="298f6-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="298f6-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="298f6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="298f6-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="298f6-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="298f6-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="298f6-111">Requirements</span></span>  
 <span data-ttu-id="298f6-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="298f6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="298f6-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="298f6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="298f6-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="298f6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="298f6-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="298f6-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="298f6-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="298f6-116">See also</span></span>

- [<span data-ttu-id="298f6-117">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="298f6-117">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="298f6-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="298f6-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
