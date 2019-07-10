---
title: ICorDebugInstanceFieldSymbol::GetName メソッド
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 338f68a6ffc1c23508f12b344008fecce01bbf7d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760262"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="527da-102">ICorDebugInstanceFieldSymbol::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="527da-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="527da-103">インスタンス フィールドの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="527da-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="527da-104">構文</span><span class="sxs-lookup"><span data-stu-id="527da-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="527da-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="527da-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="527da-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="527da-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="527da-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="527da-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="527da-108">[out] 返される名前を格納する文字配列。</span><span class="sxs-lookup"><span data-stu-id="527da-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="527da-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="527da-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="527da-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="527da-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="527da-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="527da-111">Requirements</span></span>  
 <span data-ttu-id="527da-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="527da-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="527da-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="527da-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="527da-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="527da-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="527da-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="527da-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="527da-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="527da-116">See also</span></span>

- [<span data-ttu-id="527da-117">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="527da-117">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="527da-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="527da-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
