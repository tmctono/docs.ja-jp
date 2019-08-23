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
ms.openlocfilehash: d8fe1a25c4bc1f5e19f49f0d660d0aad5a180ea2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911889"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="fff25-102">ICorDebugModule2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fff25-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="fff25-103">モジュールインターフェイスの論理拡張機能として機能します。</span><span class="sxs-lookup"><span data-stu-id="fff25-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fff25-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="fff25-104">Methods</span></span>  
  
|<span data-ttu-id="fff25-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="fff25-105">Method</span></span>|<span data-ttu-id="fff25-106">説明</span><span class="sxs-lookup"><span data-stu-id="fff25-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fff25-107">ApplyChanges メソッド</span><span class="sxs-lookup"><span data-stu-id="fff25-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="fff25-108">メタデータの変更と、Microsoft 中間言語 (MSIL) コードの変更を実行中のプロセスに適用します。</span><span class="sxs-lookup"><span data-stu-id="fff25-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="fff25-109">GetJITCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="fff25-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="fff25-110">この`ICorDebugModule2`の just-in-time (JIT) コンパイルを制御するフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="fff25-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="fff25-111">ResolveAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="fff25-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="fff25-112">指定したメタデータトークンによって参照されるアセンブリを解決します。</span><span class="sxs-lookup"><span data-stu-id="fff25-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="fff25-113">SetJITCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="fff25-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="fff25-114">この`ICorDebugModule2`の JIT コンパイルを制御するフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="fff25-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="fff25-115">SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="fff25-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="fff25-116">この`ICorDebugModule2`のすべてのクラスのすべてのメソッドのマイコードのみ (JMC) の状態を、指定した値に設定し`pTokens`ます。ただし、逆の値に設定されている配列内のすべてのメソッドを除きます。</span><span class="sxs-lookup"><span data-stu-id="fff25-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fff25-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="fff25-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fff25-118">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fff25-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fff25-119">必要条件</span><span class="sxs-lookup"><span data-stu-id="fff25-119">Requirements</span></span>  
 <span data-ttu-id="fff25-120">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fff25-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fff25-121">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="fff25-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fff25-122">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="fff25-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fff25-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fff25-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fff25-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="fff25-124">See also</span></span>

- [<span data-ttu-id="fff25-125">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fff25-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
