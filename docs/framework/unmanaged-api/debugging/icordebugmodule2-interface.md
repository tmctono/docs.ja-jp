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
ms.openlocfilehash: 7b98302985d9d54599ea8ea2e01dc2503c468d58
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210229"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="e6bba-102">ICorDebugModule2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6bba-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="e6bba-103">モジュールインターフェイスの論理拡張機能として機能します。</span><span class="sxs-lookup"><span data-stu-id="e6bba-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6bba-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e6bba-104">Methods</span></span>  
  
|<span data-ttu-id="e6bba-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e6bba-105">Method</span></span>|<span data-ttu-id="e6bba-106">説明</span><span class="sxs-lookup"><span data-stu-id="e6bba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6bba-107">ApplyChanges メソッド</span><span class="sxs-lookup"><span data-stu-id="e6bba-107">ApplyChanges Method</span></span>](icordebugmodule2-applychanges-method.md)|<span data-ttu-id="e6bba-108">メタデータの変更と、Microsoft 中間言語 (MSIL) コードの変更を実行中のプロセスに適用します。</span><span class="sxs-lookup"><span data-stu-id="e6bba-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="e6bba-109">GetJITCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="e6bba-109">GetJITCompilerFlags Method</span></span>](icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="e6bba-110">このの just-in-time (JIT) コンパイルを制御するフラグを取得し `ICorDebugModule2` ます。</span><span class="sxs-lookup"><span data-stu-id="e6bba-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="e6bba-111">ResolveAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="e6bba-111">ResolveAssembly Method</span></span>](icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="e6bba-112">指定したメタデータトークンによって参照されるアセンブリを解決します。</span><span class="sxs-lookup"><span data-stu-id="e6bba-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="e6bba-113">SetJITCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="e6bba-113">SetJITCompilerFlags Method</span></span>](icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="e6bba-114">このの JIT コンパイルを制御するフラグを設定 `ICorDebugModule2` します。</span><span class="sxs-lookup"><span data-stu-id="e6bba-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="e6bba-115">SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="e6bba-115">SetJMCStatus Method</span></span>](icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="e6bba-116">こののすべてのクラスのすべてのメソッドのマイコードのみ (JMC) の状態を、 `ICorDebugModule2` 指定した値に設定し `pTokens` ます。ただし、逆の値に設定されている配列内のすべてのメソッドを除きます。</span><span class="sxs-lookup"><span data-stu-id="e6bba-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6bba-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="e6bba-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6bba-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e6bba-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6bba-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="e6bba-119">Requirements</span></span>  
 <span data-ttu-id="e6bba-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6bba-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6bba-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6bba-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6bba-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6bba-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6bba-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6bba-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6bba-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6bba-124">See also</span></span>

- [<span data-ttu-id="e6bba-125">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6bba-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
