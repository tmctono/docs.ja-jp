---
title: ICorDebugILFrame::GetIP メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
ms.openlocfilehash: 7e1605eede55360e72d65da6744bc1dcce4f107f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130992"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="929b9-102">ICorDebugILFrame::GetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="929b9-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="929b9-103">命令ポインターの値と、命令ポインターの値が取得された方法を示すビットごとの組み合わせ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="929b9-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="929b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="929b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="929b9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="929b9-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="929b9-106">入出力命令ポインターの値。</span><span class="sxs-lookup"><span data-stu-id="929b9-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="929b9-107">入出力命令ポインターの値の取得方法を示す CorDebugMappingResult 列挙値のビットごとの組み合わせへのポインター。</span><span class="sxs-lookup"><span data-stu-id="929b9-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="929b9-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="929b9-108">Remarks</span></span>  
 <span data-ttu-id="929b9-109">命令ポインターの値は、関数の MSIL (Microsoft 中間言語) コードへのスタックフレームのオフセットです。</span><span class="sxs-lookup"><span data-stu-id="929b9-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="929b9-110">スタックフレームがアクティブな場合、このアドレスは次に実行する命令になります。</span><span class="sxs-lookup"><span data-stu-id="929b9-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="929b9-111">スタックフレームがアクティブでない場合、このアドレスはスタックフレームが再アクティブ化されたときに次に実行される命令になります。</span><span class="sxs-lookup"><span data-stu-id="929b9-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="929b9-112">このフレームが just-in-time (JIT) でコンパイルされたフレームである場合、命令ポインターの値は、実際のネイティブ命令ポインターから逆方向にマッピングすることによって決定されます。したがって、値は概数にすぎない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="929b9-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="929b9-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="929b9-113">Requirements</span></span>  
 <span data-ttu-id="929b9-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="929b9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="929b9-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="929b9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="929b9-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="929b9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="929b9-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="929b9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
