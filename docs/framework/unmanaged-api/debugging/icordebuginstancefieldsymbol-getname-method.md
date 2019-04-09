---
title: ICorDebugInstanceFieldSymbol::GetName メソッド
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d23bf14fbb3d75534ac2d4a43eca0fbf3e994ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161396"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="69bce-102">ICorDebugInstanceFieldSymbol::GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="69bce-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="69bce-103">インスタンス フィールドの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="69bce-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69bce-104">構文</span><span class="sxs-lookup"><span data-stu-id="69bce-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69bce-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="69bce-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="69bce-106">[in] `szName` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="69bce-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="69bce-107">[out] `szName` バッファーに実際に書き込まれた文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="69bce-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="69bce-108">[out] 返される名前を格納する文字配列。</span><span class="sxs-lookup"><span data-stu-id="69bce-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69bce-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="69bce-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69bce-110">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="69bce-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69bce-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="69bce-111">Requirements</span></span>  
 <span data-ttu-id="69bce-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69bce-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69bce-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69bce-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69bce-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69bce-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="69bce-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="69bce-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="69bce-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="69bce-116">See also</span></span>

- [<span data-ttu-id="69bce-117">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="69bce-117">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="69bce-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="69bce-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
