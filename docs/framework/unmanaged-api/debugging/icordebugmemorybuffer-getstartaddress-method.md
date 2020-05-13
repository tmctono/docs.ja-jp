---
title: ICorDebugMemoryBuffer::GetStartAddress メソッド
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: 47369c744ee42fb03857a3e69063a04e4f509d0d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212348"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="f1441-102">ICorDebugMemoryBuffer::GetStartAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="f1441-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="f1441-103">メモリ バッファーの開始アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f1441-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1441-104">構文</span><span class="sxs-lookup"><span data-stu-id="f1441-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1441-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1441-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="f1441-106">[out] メモリ バッファーの開始アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f1441-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1441-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1441-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="f1441-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1441-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1441-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="f1441-109">Requirements</span></span>  
 <span data-ttu-id="f1441-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1441-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1441-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1441-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1441-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1441-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1441-113">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1441-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1441-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1441-114">See also</span></span>

- [<span data-ttu-id="f1441-115">ICorDebugMemoryBuffer インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1441-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="f1441-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1441-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
