---
title: ICorDebugVariableSymbol::GetSize メソッド
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: 6d60dbdefd09770fd5a18653c5118469323581e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790911"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="f7a0e-102">ICorDebugVariableSymbol::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="f7a0e-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="f7a0e-103">変数のサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="f7a0e-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7a0e-104">構文</span><span class="sxs-lookup"><span data-stu-id="f7a0e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7a0e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7a0e-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="f7a0e-106">変数のサイズが格納されている 32 ビットの符号なし整数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f7a0e-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7a0e-107">コメント</span><span class="sxs-lookup"><span data-stu-id="f7a0e-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f7a0e-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7a0e-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7a0e-109">要件</span><span class="sxs-lookup"><span data-stu-id="f7a0e-109">Requirements</span></span>  
 <span data-ttu-id="f7a0e-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7a0e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7a0e-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7a0e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7a0e-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7a0e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7a0e-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7a0e-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a0e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7a0e-114">See also</span></span>

- [<span data-ttu-id="f7a0e-115">ICorDebugVariableSymbol インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7a0e-115">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="f7a0e-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f7a0e-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
