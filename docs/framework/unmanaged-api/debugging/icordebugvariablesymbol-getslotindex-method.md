---
title: ICorDebugVariableSymbol::GetSlotIndex メソッド
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: affe67006c9e37d55b0f9d107c92441da44c9ab8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138794"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="c0638-102">ICorDebugVariableSymbol::GetSlotIndex メソッド</span><span class="sxs-lookup"><span data-stu-id="c0638-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="c0638-103">ローカル変数のマネージド スロット インデックスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c0638-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0638-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0638-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0638-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0638-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="c0638-106">[out] ローカル変数のスロット インデックスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c0638-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0638-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0638-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="c0638-108">成功した場合。</span><span class="sxs-lookup"><span data-stu-id="c0638-108">if successful.</span></span> `E_FAIL` <span data-ttu-id="c0638-109">変数が関数の引数である場合。</span><span class="sxs-lookup"><span data-stu-id="c0638-109">if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0638-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0638-110">Remarks</span></span>  
 <span data-ttu-id="c0638-111">ローカル変数のマネージド スロット インデックスを使用すると、変数のメタデータ情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="c0638-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0638-112">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0638-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0638-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="c0638-113">Requirements</span></span>  
 <span data-ttu-id="c0638-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0638-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0638-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0638-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0638-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0638-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c0638-117">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c0638-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c0638-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0638-118">See also</span></span>

- [<span data-ttu-id="c0638-119">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0638-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="c0638-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0638-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
