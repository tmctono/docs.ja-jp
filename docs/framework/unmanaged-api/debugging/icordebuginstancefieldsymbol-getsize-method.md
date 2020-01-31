---
title: ICorDebugInstanceFieldSymbol::GetSize メソッド
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: eb70c441441954e2ffce6ca832c58369c606b128
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782277"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="77a06-102">ICorDebugInstanceFieldSymbol::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="77a06-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="77a06-103">インスタンス フィールドのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="77a06-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77a06-104">構文</span><span class="sxs-lookup"><span data-stu-id="77a06-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77a06-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="77a06-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="77a06-106">[out] フィールドの長さへのポインター。</span><span class="sxs-lookup"><span data-stu-id="77a06-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77a06-107">コメント</span><span class="sxs-lookup"><span data-stu-id="77a06-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77a06-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="77a06-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77a06-109">要件</span><span class="sxs-lookup"><span data-stu-id="77a06-109">Requirements</span></span>  
 <span data-ttu-id="77a06-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77a06-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77a06-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77a06-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77a06-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77a06-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77a06-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77a06-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77a06-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="77a06-114">See also</span></span>

- [<span data-ttu-id="77a06-115">ICorDebugInstanceFieldSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77a06-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="77a06-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="77a06-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
