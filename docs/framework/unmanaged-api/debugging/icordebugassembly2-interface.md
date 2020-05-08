---
title: ICorDebugAssembly2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2
helpviewer_keywords:
- ICorDebugAssembly2 interface [.NET Framework debugging]
ms.assetid: c0766e29-e573-4f9a-a928-167d1de5aa7e
topic_type:
- apiref
ms.openlocfilehash: 23b38f86cd81fb0161e50b60b40bed0ba0b423b2
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894880"
---
# <a name="icordebugassembly2-interface"></a><span data-ttu-id="306e5-102">ICorDebugAssembly2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="306e5-102">ICorDebugAssembly2 Interface</span></span>

<span data-ttu-id="306e5-103">アセンブリを表します。</span><span class="sxs-lookup"><span data-stu-id="306e5-103">Represents an assembly.</span></span> <span data-ttu-id="306e5-104">このインターフェイスは、というアセンブリインターフェイスの拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="306e5-104">This interface is an extension of the ICorDebugAssembly interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="306e5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="306e5-105">Methods</span></span>  
  
|<span data-ttu-id="306e5-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="306e5-106">Method</span></span>|<span data-ttu-id="306e5-107">説明</span><span class="sxs-lookup"><span data-stu-id="306e5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="306e5-108">IsFullyTrusted メソッド</span><span class="sxs-lookup"><span data-stu-id="306e5-108">IsFullyTrusted Method</span></span>](icordebugassembly2-isfullytrusted-method.md)|<span data-ttu-id="306e5-109">アセンブリにランタイムセキュリティシステムによる完全信頼が付与されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="306e5-109">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="306e5-110">解説</span><span class="sxs-lookup"><span data-stu-id="306e5-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="306e5-111">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="306e5-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="306e5-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="306e5-112">Requirements</span></span>  
 <span data-ttu-id="306e5-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="306e5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="306e5-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="306e5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="306e5-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="306e5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="306e5-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="306e5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306e5-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="306e5-117">See also</span></span>

- [<span data-ttu-id="306e5-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="306e5-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
