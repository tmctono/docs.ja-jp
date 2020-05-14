---
title: ICorDebugVariableSymbol::GetName メソッド
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: ea414a39e140c74df736764dbbb1bb3934bda78f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397126"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="38500-102">ICorDebugVariableSymbol::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="38500-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="38500-103">変数の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="38500-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38500-104">構文</span><span class="sxs-lookup"><span data-stu-id="38500-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38500-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="38500-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="38500-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="38500-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="38500-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="38500-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="38500-108">変数名が格納されている文字配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="38500-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38500-109">解説</span><span class="sxs-lookup"><span data-stu-id="38500-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="38500-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="38500-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38500-111">要件</span><span class="sxs-lookup"><span data-stu-id="38500-111">Requirements</span></span>  
 <span data-ttu-id="38500-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38500-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38500-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38500-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38500-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38500-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38500-115">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38500-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38500-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="38500-116">See also</span></span>

- [<span data-ttu-id="38500-117">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="38500-117">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="38500-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="38500-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
