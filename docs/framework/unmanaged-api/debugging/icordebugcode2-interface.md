---
title: ICorDebugCode2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cb7be64089a55e7b653fcd6272219abba311af8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960810"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="929ae-102">ICorDebugCode2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="929ae-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="929ae-103">"コード例" の機能を拡張するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="929ae-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="929ae-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="929ae-104">Methods</span></span>  
  
|<span data-ttu-id="929ae-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="929ae-105">Method</span></span>|<span data-ttu-id="929ae-106">説明</span><span class="sxs-lookup"><span data-stu-id="929ae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="929ae-107">GetCodeChunks メソッド</span><span class="sxs-lookup"><span data-stu-id="929ae-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="929ae-108">このコード オブジェクトを構成しているコード チャンクを取得します。</span><span class="sxs-lookup"><span data-stu-id="929ae-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="929ae-109">GetCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="929ae-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="929ae-110">このコード オブジェクトが Just-In-Time (JIT) コンパイルされたとき、またはネイティブ イメージ ジェネレーター (Ngen.exe) を使用して生成されたときの条件を指定するフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="929ae-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="929ae-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="929ae-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="929ae-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="929ae-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="929ae-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="929ae-113">Requirements</span></span>  
 <span data-ttu-id="929ae-114">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="929ae-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="929ae-115">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="929ae-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="929ae-116">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="929ae-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="929ae-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="929ae-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929ae-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="929ae-118">See also</span></span>

- [<span data-ttu-id="929ae-119">ICorDebugCode3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="929ae-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="929ae-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="929ae-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
