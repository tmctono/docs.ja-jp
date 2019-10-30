---
title: ICorDebugILFrame4 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame4
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type:
- apiref
ms.openlocfilehash: 010d73309ae21f9a593f72533691bdd95fbd4132
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130847"
---
# <a name="icordebugilframe4-interface"></a><span data-ttu-id="96da7-102">ICorDebugILFrame4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96da7-102">ICorDebugILFrame4 Interface</span></span>
<span data-ttu-id="96da7-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="96da7-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="96da7-104">ローカル変数にアクセスできるようにするメソッドおよび中間言語 (IL) コードのスタック フレームのコードを提供します。</span><span class="sxs-lookup"><span data-stu-id="96da7-104">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="96da7-105">パラメーターは、プロファイラーの ReJIT インストルメンテーションに追加される変数およびコードへデバッガーがアクセスできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="96da7-105">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="96da7-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="96da7-106">Methods</span></span>  
  
|<span data-ttu-id="96da7-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="96da7-107">Method</span></span>|<span data-ttu-id="96da7-108">説明</span><span class="sxs-lookup"><span data-stu-id="96da7-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="96da7-109">EnumerateLocalVariablesEx メソッド</span><span class="sxs-lookup"><span data-stu-id="96da7-109">EnumerateLocalVariablesEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)|<span data-ttu-id="96da7-110">現在のフレームで使用可能なローカル変数の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="96da7-110">Returns a list of the local variables available in the current frame.</span></span>|  
|[<span data-ttu-id="96da7-111">GetCodeEx メソッド</span><span class="sxs-lookup"><span data-stu-id="96da7-111">GetCodeEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)|<span data-ttu-id="96da7-112">このスタック フレームが実行するコードを返します。</span><span class="sxs-lookup"><span data-stu-id="96da7-112">Returns the code that this stack frame is running.</span></span>|  
|[<span data-ttu-id="96da7-113">GetLocalVariableEx メソッド</span><span class="sxs-lookup"><span data-stu-id="96da7-113">GetLocalVariableEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)|<span data-ttu-id="96da7-114">IL フレーム内のローカル変数の値を返します。</span><span class="sxs-lookup"><span data-stu-id="96da7-114">Returns the value of a local variable in the IL frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96da7-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="96da7-115">Remarks</span></span>  
 <span data-ttu-id="96da7-116">これらのメソッドは、 [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)、 [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)、および[getlocalvariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)の各メソッドによって提供される機能に加えて機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="96da7-116">These methods offer functionality in addition to that provided by the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md), [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md), and [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) methods.</span></span> <span data-ttu-id="96da7-117">各メソッドには、追加のローカル変数またはプロファイラーの ReJIT 要求によって定義されているコードが参照可能かどうかを指定する `flags` パラメーターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="96da7-117">Each method includes a `flags` parameter that specifies whether additional local variables or code defined by a profiler's ReJIT request are visible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96da7-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="96da7-118">Requirements</span></span>  
 <span data-ttu-id="96da7-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96da7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96da7-120">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96da7-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96da7-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96da7-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96da7-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96da7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96da7-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="96da7-123">See also</span></span>

- [<span data-ttu-id="96da7-124">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="96da7-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="96da7-125">デバッグ</span><span class="sxs-lookup"><span data-stu-id="96da7-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
