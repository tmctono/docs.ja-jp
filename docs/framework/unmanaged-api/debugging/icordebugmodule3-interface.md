---
title: ICorDebugModule3 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugModule3
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3
helpviewer_keywords:
- ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e51ff64115ce3417087eee6845aa802ad64f2a72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961005"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="b1b63-102">ICorDebugModule3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1b63-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="b1b63-103">動的モジュールのシンボル リーダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1b63-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1b63-104">構文</span><span class="sxs-lookup"><span data-stu-id="b1b63-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b1b63-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b1b63-105">Methods</span></span>  
  
|<span data-ttu-id="b1b63-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="b1b63-106">Method</span></span>|<span data-ttu-id="b1b63-107">説明</span><span class="sxs-lookup"><span data-stu-id="b1b63-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b1b63-108">ICorDebugModule3::CreateReaderForInMemorySymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="b1b63-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="b1b63-109">動的モジュールのシンボルリーダー (通常は[ISymUnmanagedReader インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) を作成します。</span><span class="sxs-lookup"><span data-stu-id="b1b63-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1b63-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b1b63-110">Remarks</span></span>  
 <span data-ttu-id="b1b63-111">このインターフェイスは、"ICorDebugModule2" インターフェイスと "" インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="b1b63-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1b63-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b1b63-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1b63-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="b1b63-113">Requirements</span></span>  
 <span data-ttu-id="b1b63-114">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1b63-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1b63-115">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="b1b63-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1b63-116">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="b1b63-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1b63-117">**.NET Framework のバージョン:** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="b1b63-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b1b63-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1b63-118">See also</span></span>

- [<span data-ttu-id="b1b63-119">ICorDebugRemoteTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1b63-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="b1b63-120">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1b63-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="b1b63-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1b63-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
