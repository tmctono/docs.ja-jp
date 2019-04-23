---
title: ICorDebugInstanceFieldSymbol::GetOffset メソッド
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8ea777755aebb59f3e865df26c38c74ef68ae31
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203874"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="1e4d1-102">ICorDebugInstanceFieldSymbol::GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="1e4d1-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="1e4d1-103">このインスタンス フィールドの親クラスにおける、このインスタンス フィールドのオフセット (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="1e4d1-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e4d1-104">構文</span><span class="sxs-lookup"><span data-stu-id="1e4d1-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e4d1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1e4d1-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="1e4d1-106">このインスタンス フィールドの親クラスにおける、このフィールドのオフセットのバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1e4d1-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e4d1-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1e4d1-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e4d1-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e4d1-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e4d1-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="1e4d1-109">Requirements</span></span>  
 <span data-ttu-id="1e4d1-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e4d1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e4d1-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e4d1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e4d1-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e4d1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e4d1-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e4d1-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e4d1-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e4d1-114">See also</span></span>

- [<span data-ttu-id="1e4d1-115">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e4d1-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="1e4d1-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1e4d1-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
