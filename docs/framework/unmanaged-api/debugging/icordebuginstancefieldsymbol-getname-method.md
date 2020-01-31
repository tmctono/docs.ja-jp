---
title: ICorDebugInstanceFieldSymbol::GetName メソッド
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: 05914863dfbc2aca608a5d74f298f81c64345fe8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782385"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="2de9b-102">ICorDebugInstanceFieldSymbol::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="2de9b-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="2de9b-103">インスタンス フィールドの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="2de9b-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2de9b-104">構文</span><span class="sxs-lookup"><span data-stu-id="2de9b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2de9b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2de9b-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="2de9b-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="2de9b-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2de9b-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2de9b-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="2de9b-108">[out] 返される名前を格納する文字配列。</span><span class="sxs-lookup"><span data-stu-id="2de9b-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2de9b-109">コメント</span><span class="sxs-lookup"><span data-stu-id="2de9b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2de9b-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2de9b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2de9b-111">要件</span><span class="sxs-lookup"><span data-stu-id="2de9b-111">Requirements</span></span>  
 <span data-ttu-id="2de9b-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2de9b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2de9b-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2de9b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2de9b-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2de9b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2de9b-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2de9b-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2de9b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2de9b-116">See also</span></span>

- [<span data-ttu-id="2de9b-117">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2de9b-117">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="2de9b-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2de9b-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
