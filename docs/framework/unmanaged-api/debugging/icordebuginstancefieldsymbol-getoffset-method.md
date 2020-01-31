---
title: ICorDebugInstanceFieldSymbol::GetOffset メソッド
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: f7c13d397b39698bdf1a22f14820680e1fd0a25f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782299"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="0c91f-102">ICorDebugInstanceFieldSymbol::GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="0c91f-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="0c91f-103">このインスタンス フィールドの親クラスにおける、このインスタンス フィールドのオフセット (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="0c91f-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c91f-104">構文</span><span class="sxs-lookup"><span data-stu-id="0c91f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c91f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c91f-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="0c91f-106">このインスタンス フィールドの親クラスにおける、このフィールドのオフセットのバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0c91f-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c91f-107">コメント</span><span class="sxs-lookup"><span data-stu-id="0c91f-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c91f-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c91f-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c91f-109">要件</span><span class="sxs-lookup"><span data-stu-id="0c91f-109">Requirements</span></span>  
 <span data-ttu-id="0c91f-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c91f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c91f-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c91f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c91f-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c91f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c91f-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c91f-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c91f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c91f-114">See also</span></span>

- [<span data-ttu-id="0c91f-115">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0c91f-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="0c91f-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0c91f-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
