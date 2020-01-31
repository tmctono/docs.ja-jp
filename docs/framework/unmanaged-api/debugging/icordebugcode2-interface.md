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
ms.openlocfilehash: a9ce778cfa1aed4dcf6117c4fe2eca23ccda37a3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777946"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="539d5-102">ICorDebugCode2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="539d5-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="539d5-103">"コード例" の機能を拡張するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="539d5-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="539d5-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="539d5-104">Methods</span></span>  
  
|<span data-ttu-id="539d5-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="539d5-105">Method</span></span>|<span data-ttu-id="539d5-106">説明</span><span class="sxs-lookup"><span data-stu-id="539d5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="539d5-107">GetCodeChunks メソッド</span><span class="sxs-lookup"><span data-stu-id="539d5-107">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="539d5-108">このコード オブジェクトを構成しているコード チャンクを取得します。</span><span class="sxs-lookup"><span data-stu-id="539d5-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="539d5-109">GetCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="539d5-109">GetCompilerFlags Method</span></span>](icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="539d5-110">このコード オブジェクトが Just-In-Time (JIT) コンパイルされたとき、またはネイティブ イメージ ジェネレーター (Ngen.exe) を使用して生成されたときの条件を指定するフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="539d5-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="539d5-111">コメント</span><span class="sxs-lookup"><span data-stu-id="539d5-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="539d5-112">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="539d5-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="539d5-113">要件</span><span class="sxs-lookup"><span data-stu-id="539d5-113">Requirements</span></span>  
 <span data-ttu-id="539d5-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="539d5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="539d5-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="539d5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="539d5-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="539d5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="539d5-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="539d5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="539d5-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="539d5-118">See also</span></span>

- [<span data-ttu-id="539d5-119">ICorDebugCode3 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="539d5-119">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="539d5-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="539d5-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
