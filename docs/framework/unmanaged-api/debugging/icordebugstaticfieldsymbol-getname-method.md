---
title: ICorDebugStaticFieldSymbol::GetName メソッド
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: b1f5ca266f51df730dfb840c7bf003c47f31ece9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178509"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="56c59-102">ICorDebugStaticFieldSymbol::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="56c59-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="56c59-103">静的フィールドの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="56c59-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56c59-104">構文</span><span class="sxs-lookup"><span data-stu-id="56c59-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56c59-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="56c59-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="56c59-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="56c59-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="56c59-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="56c59-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="56c59-108">[out] 返される名前を格納する文字配列。</span><span class="sxs-lookup"><span data-stu-id="56c59-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56c59-109">解説</span><span class="sxs-lookup"><span data-stu-id="56c59-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="56c59-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="56c59-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56c59-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="56c59-111">Requirements</span></span>  
 <span data-ttu-id="56c59-112">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56c59-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56c59-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56c59-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56c59-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56c59-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56c59-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56c59-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56c59-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="56c59-116">See also</span></span>

- [<span data-ttu-id="56c59-117">ICorDebugStaticFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56c59-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="56c59-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56c59-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
