---
title: ICorDebugMetaDataLocator インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator
helpviewer_keywords:
- ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: 287f5ecd-863f-4090-a615-077859f0257b
topic_type:
- apiref
ms.openlocfilehash: dd31bf458dde043a04e24251cedcac585fd385f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793040"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="ea28a-102">ICorDebugMetaDataLocator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea28a-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="ea28a-103">デバッガーにメタデータ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ea28a-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ea28a-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="ea28a-104">Methods</span></span>  
  
|<span data-ttu-id="ea28a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ea28a-105">Method</span></span>|<span data-ttu-id="ea28a-106">説明</span><span class="sxs-lookup"><span data-stu-id="ea28a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ea28a-107">GetMetadata メソッド</span><span class="sxs-lookup"><span data-stu-id="ea28a-107">GetMetaData Method</span></span>](icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="ea28a-108">デバッガーが要求した操作を完了するために必要となるメタデータが含まれているモジュールの完全パスを返すように、デバッガーに求めます。</span><span class="sxs-lookup"><span data-stu-id="ea28a-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea28a-109">コメント</span><span class="sxs-lookup"><span data-stu-id="ea28a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea28a-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ea28a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea28a-111">要件</span><span class="sxs-lookup"><span data-stu-id="ea28a-111">Requirements</span></span>  
 <span data-ttu-id="ea28a-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea28a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea28a-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea28a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea28a-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea28a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea28a-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea28a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea28a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea28a-116">See also</span></span>

- [<span data-ttu-id="ea28a-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea28a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ea28a-118">デバッグ</span><span class="sxs-lookup"><span data-stu-id="ea28a-118">Debugging</span></span>](index.md)
