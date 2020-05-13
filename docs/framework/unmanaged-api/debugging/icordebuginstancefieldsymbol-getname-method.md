---
title: ICorDebugInstanceFieldSymbol::GetName メソッド
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: 0f1b648f494a2f2676374cfd13db46b70f1f195c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209995"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="97f14-102">ICorDebugInstanceFieldSymbol::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="97f14-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="97f14-103">インスタンス フィールドの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="97f14-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97f14-104">構文</span><span class="sxs-lookup"><span data-stu-id="97f14-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97f14-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="97f14-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="97f14-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="97f14-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="97f14-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="97f14-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="97f14-108">[out] 返される名前を格納する文字配列。</span><span class="sxs-lookup"><span data-stu-id="97f14-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97f14-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="97f14-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97f14-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="97f14-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97f14-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="97f14-111">Requirements</span></span>  
 <span data-ttu-id="97f14-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97f14-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97f14-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97f14-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97f14-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97f14-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97f14-115">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97f14-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97f14-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="97f14-116">See also</span></span>

- [<span data-ttu-id="97f14-117">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="97f14-117">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="97f14-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="97f14-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
