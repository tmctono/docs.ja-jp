---
title: ICorDebugVariableSymbol::GetName メソッド
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f514acbd772c9d33ec4372cfaccb778d6bb41eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170171"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="97d21-102">ICorDebugVariableSymbol::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="97d21-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="97d21-103">変数の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="97d21-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97d21-104">構文</span><span class="sxs-lookup"><span data-stu-id="97d21-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97d21-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="97d21-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="97d21-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="97d21-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="97d21-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="97d21-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="97d21-108">変数名が格納されている文字配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="97d21-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97d21-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="97d21-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97d21-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="97d21-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97d21-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="97d21-111">Requirements</span></span>  
 <span data-ttu-id="97d21-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97d21-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97d21-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97d21-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97d21-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97d21-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="97d21-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="97d21-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="97d21-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="97d21-116">See also</span></span>

- [<span data-ttu-id="97d21-117">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="97d21-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="97d21-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="97d21-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
