---
title: ICorDebugStaticFieldSymbol::GetName メソッド
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: 0e4c52ff1ae6113ee2c3990a9d91682e10141902
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791827"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="facb2-102">ICorDebugStaticFieldSymbol::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="facb2-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="facb2-103">静的フィールドの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="facb2-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="facb2-104">構文</span><span class="sxs-lookup"><span data-stu-id="facb2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="facb2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="facb2-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="facb2-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="facb2-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="facb2-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="facb2-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="facb2-108">[out] 返される名前を格納する文字配列。</span><span class="sxs-lookup"><span data-stu-id="facb2-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="facb2-109">コメント</span><span class="sxs-lookup"><span data-stu-id="facb2-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="facb2-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="facb2-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="facb2-111">要件</span><span class="sxs-lookup"><span data-stu-id="facb2-111">Requirements</span></span>  
 <span data-ttu-id="facb2-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="facb2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="facb2-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="facb2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="facb2-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="facb2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="facb2-115">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="facb2-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="facb2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="facb2-116">See also</span></span>

- [<span data-ttu-id="facb2-117">ICorDebugStaticFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="facb2-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="facb2-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="facb2-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
