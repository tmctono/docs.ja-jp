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
ms.openlocfilehash: a3a1b658f4ab05c7029de907882fe5ab2513ccd8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127883"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="317fc-102">ICorDebugModule2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="317fc-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="317fc-103">モジュールインターフェイスの論理拡張機能として機能します。</span><span class="sxs-lookup"><span data-stu-id="317fc-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="317fc-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="317fc-104">Methods</span></span>  
  
|<span data-ttu-id="317fc-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="317fc-105">Method</span></span>|<span data-ttu-id="317fc-106">説明</span><span class="sxs-lookup"><span data-stu-id="317fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="317fc-107">ApplyChanges メソッド</span><span class="sxs-lookup"><span data-stu-id="317fc-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="317fc-108">メタデータの変更と、Microsoft 中間言語 (MSIL) コードの変更を実行中のプロセスに適用します。</span><span class="sxs-lookup"><span data-stu-id="317fc-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="317fc-109">GetJITCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="317fc-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="317fc-110">この `ICorDebugModule2`の just-in-time (JIT) コンパイルを制御するフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="317fc-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="317fc-111">ResolveAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="317fc-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="317fc-112">指定したメタデータトークンによって参照されるアセンブリを解決します。</span><span class="sxs-lookup"><span data-stu-id="317fc-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="317fc-113">SetJITCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="317fc-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="317fc-114">この `ICorDebugModule2`の JIT コンパイルを制御するフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="317fc-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="317fc-115">SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="317fc-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="317fc-116">この `ICorDebugModule2` 内のすべてのクラスのすべてのメソッドのマイコードのみ (JMC) 状態を、指定した値に設定します。ただし、逆の値に設定するのは、`pTokens` 配列内のすべてのメソッドです。</span><span class="sxs-lookup"><span data-stu-id="317fc-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="317fc-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="317fc-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="317fc-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="317fc-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="317fc-119">［要件］</span><span class="sxs-lookup"><span data-stu-id="317fc-119">Requirements</span></span>  
 <span data-ttu-id="317fc-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="317fc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="317fc-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="317fc-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="317fc-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="317fc-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="317fc-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="317fc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="317fc-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="317fc-124">See also</span></span>

- [<span data-ttu-id="317fc-125">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="317fc-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
