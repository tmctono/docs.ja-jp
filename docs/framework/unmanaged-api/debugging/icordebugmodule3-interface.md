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
ms.openlocfilehash: a340086be042c790ae7bf750759ff80f7c9eaf23
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942442"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="329f3-102">ICorDebugModule3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="329f3-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="329f3-103">動的モジュールのシンボル リーダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="329f3-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="329f3-104">構文</span><span class="sxs-lookup"><span data-stu-id="329f3-104">Syntax</span></span>  
  
```  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="329f3-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="329f3-105">Methods</span></span>  
  
|<span data-ttu-id="329f3-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="329f3-106">Method</span></span>|<span data-ttu-id="329f3-107">説明</span><span class="sxs-lookup"><span data-stu-id="329f3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="329f3-108">ICorDebugModule3::CreateReaderForInMemorySymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="329f3-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="329f3-109">シンボル リーダーを作成します (通常[ISymUnmanagedReader インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) の動的モジュール。</span><span class="sxs-lookup"><span data-stu-id="329f3-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="329f3-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="329f3-110">Remarks</span></span>  
 <span data-ttu-id="329f3-111">このインターフェイスは、"ICorDebugModule"および"ICorDebugModule2"インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="329f3-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="329f3-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="329f3-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="329f3-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="329f3-113">Requirements</span></span>  
 <span data-ttu-id="329f3-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="329f3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="329f3-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="329f3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="329f3-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="329f3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="329f3-117">**.NET framework のバージョン:** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="329f3-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="329f3-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="329f3-118">See also</span></span>

- [<span data-ttu-id="329f3-119">ICorDebugRemoteTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="329f3-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="329f3-120">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="329f3-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="329f3-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="329f3-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
