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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 192f2476aff91d3a8302d070852ab2a3722d137c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970130"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="a1bbc-102">ICorDebugModule2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1bbc-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="a1bbc-103">ICorDebugModule インターフェイスを論理的に拡張として機能します。</span><span class="sxs-lookup"><span data-stu-id="a1bbc-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1bbc-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="a1bbc-104">Methods</span></span>  
  
|<span data-ttu-id="a1bbc-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="a1bbc-105">Method</span></span>|<span data-ttu-id="a1bbc-106">説明</span><span class="sxs-lookup"><span data-stu-id="a1bbc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1bbc-107">ApplyChanges メソッド</span><span class="sxs-lookup"><span data-stu-id="a1bbc-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="a1bbc-108">実行中のプロセスにメタデータの変更と Microsoft intermediate language (MSIL) コードの変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="a1bbc-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="a1bbc-109">GetJITCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="a1bbc-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="a1bbc-110">この・ イン タイム (JIT) コンパイルを制御するフラグを取得`ICorDebugModule2`します。</span><span class="sxs-lookup"><span data-stu-id="a1bbc-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="a1bbc-111">ResolveAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="a1bbc-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="a1bbc-112">指定したメタデータ トークンによって参照されるアセンブリを解決します。</span><span class="sxs-lookup"><span data-stu-id="a1bbc-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="a1bbc-113">SetJITCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="a1bbc-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="a1bbc-114">この JIT コンパイルを制御するフラグを設定して`ICorDebugModule2`します。</span><span class="sxs-lookup"><span data-stu-id="a1bbc-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="a1bbc-115">SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="a1bbc-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="a1bbc-116">これですべてのクラスのすべてのメソッドのだけマイ コードのみ (JMC) 状態を設定`ICorDebugModule2`を除く、指定した値を`pTokens`配列で、逆の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="a1bbc-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1bbc-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="a1bbc-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1bbc-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a1bbc-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1bbc-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1bbc-119">Requirements</span></span>  
 <span data-ttu-id="a1bbc-120">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1bbc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1bbc-121">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1bbc-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1bbc-122">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1bbc-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1bbc-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1bbc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1bbc-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1bbc-124">See also</span></span>
- [<span data-ttu-id="a1bbc-125">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1bbc-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
