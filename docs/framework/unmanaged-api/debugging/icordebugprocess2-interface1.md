---
title: ICorDebugProcess2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3009ee6a2ba22771a2132032744f76ca527c422
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965684"
---
# <a name="icordebugprocess2-interface"></a><span data-ttu-id="f1129-102">ICorDebugProcess2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1129-102">ICorDebugProcess2 Interface</span></span>
<span data-ttu-id="f1129-103">プロセス実行中のマネージ コードを表す ICorDebugProcess インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="f1129-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1129-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f1129-104">Methods</span></span>  
  
|<span data-ttu-id="f1129-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f1129-105">Method</span></span>|<span data-ttu-id="f1129-106">説明</span><span class="sxs-lookup"><span data-stu-id="f1129-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1129-107">ClearUnmanagedBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="f1129-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="f1129-108">以前の呼び出しによって設定された指定したオフセット位置にブレークポイントを削除`ICorDebugProcess2::SetUnmanagedBreakpoint`します。</span><span class="sxs-lookup"><span data-stu-id="f1129-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="f1129-109">GetDesiredNGENCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="f1129-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="f1129-110">これによって参照されているプロセスにイメージの読み込みに共通言語ランタイム (CLR) に設定する必要があるフラグを取得`ICorDebugProcess2`します。</span><span class="sxs-lookup"><span data-stu-id="f1129-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="f1129-111">GetReferenceValueFromGCHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="f1129-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="f1129-112">ガベージ コレクション ハンドルが、指定した管理対象のオブジェクト参照ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="f1129-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="f1129-113">GetThreadForTaskID メソッド</span><span class="sxs-lookup"><span data-stu-id="f1129-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="f1129-114">指定した識別子を持つタスクを実行するスレッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="f1129-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="f1129-115">GetVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="f1129-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="f1129-116">デバッグ中のプロセスが実行されている CLR のバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="f1129-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="f1129-117">SetDesiredNGENCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="f1129-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="f1129-118">デバッグ中のプロセスにイメージを読み込む - イン タイム (JIT) コンパイラに必要なフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="f1129-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="f1129-119">SetUnmanagedBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="f1129-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="f1129-120">ネイティブ イメージを指定したオフセットで非管理対象のブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="f1129-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1129-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1129-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1129-122">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f1129-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1129-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="f1129-123">Requirements</span></span>  
 <span data-ttu-id="f1129-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1129-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1129-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1129-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1129-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1129-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1129-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1129-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1129-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1129-128">See also</span></span>
- [<span data-ttu-id="f1129-129">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1129-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
