---
title: ICorDebugModule2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
ms.openlocfilehash: 32774aacecf3e56510bc6f0670538a44fde794c9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792986"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="0cabd-102">ICorDebugModule2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0cabd-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="0cabd-103">モジュールインターフェイスの論理拡張機能として機能します。</span><span class="sxs-lookup"><span data-stu-id="0cabd-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0cabd-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="0cabd-104">Methods</span></span>  
  
|<span data-ttu-id="0cabd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="0cabd-105">Method</span></span>|<span data-ttu-id="0cabd-106">説明</span><span class="sxs-lookup"><span data-stu-id="0cabd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0cabd-107">ApplyChanges メソッド</span><span class="sxs-lookup"><span data-stu-id="0cabd-107">ApplyChanges Method</span></span>](icordebugmodule2-applychanges-method.md)|<span data-ttu-id="0cabd-108">メタデータの変更と、Microsoft 中間言語 (MSIL) コードの変更を実行中のプロセスに適用します。</span><span class="sxs-lookup"><span data-stu-id="0cabd-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="0cabd-109">GetJITCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="0cabd-109">GetJITCompilerFlags Method</span></span>](icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="0cabd-110">この `ICorDebugModule2`の just-in-time (JIT) コンパイルを制御するフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="0cabd-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="0cabd-111">ResolveAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="0cabd-111">ResolveAssembly Method</span></span>](icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="0cabd-112">指定したメタデータトークンによって参照されるアセンブリを解決します。</span><span class="sxs-lookup"><span data-stu-id="0cabd-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="0cabd-113">SetJITCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="0cabd-113">SetJITCompilerFlags Method</span></span>](icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="0cabd-114">この `ICorDebugModule2`の JIT コンパイルを制御するフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="0cabd-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="0cabd-115">SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="0cabd-115">SetJMCStatus Method</span></span>](icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="0cabd-116">この `ICorDebugModule2` 内のすべてのクラスのすべてのメソッドのマイコードのみ (JMC) 状態を、指定した値に設定します。ただし、逆の値に設定するのは、`pTokens` 配列内のすべてのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="0cabd-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cabd-117">コメント</span><span class="sxs-lookup"><span data-stu-id="0cabd-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0cabd-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0cabd-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cabd-119">要件</span><span class="sxs-lookup"><span data-stu-id="0cabd-119">Requirements</span></span>  
 <span data-ttu-id="0cabd-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cabd-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cabd-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cabd-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cabd-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cabd-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cabd-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cabd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cabd-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="0cabd-124">See also</span></span>

- [<span data-ttu-id="0cabd-125">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0cabd-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
