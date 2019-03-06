---
title: ICorDebugStaticFieldSymbol::GetName メソッド
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffcd6971a3229423f055765b0d64258a2dfa2aa3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477935"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="98e48-102">ICorDebugStaticFieldSymbol::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="98e48-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="98e48-103">静的フィールドの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="98e48-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98e48-104">構文</span><span class="sxs-lookup"><span data-stu-id="98e48-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98e48-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98e48-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="98e48-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="98e48-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="98e48-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="98e48-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="98e48-108">[out] 返される名前を格納する文字配列。</span><span class="sxs-lookup"><span data-stu-id="98e48-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98e48-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="98e48-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98e48-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="98e48-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98e48-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="98e48-111">Requirements</span></span>  
 <span data-ttu-id="98e48-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="98e48-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98e48-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98e48-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98e48-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98e48-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98e48-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98e48-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e48-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="98e48-116">See also</span></span>
- [<span data-ttu-id="98e48-117">ICorDebugStaticFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98e48-117">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="98e48-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="98e48-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
