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
ms.openlocfilehash: f30516a8f59b90de9b4c052d92a8c88575ace3c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178824"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="1fb86-102">ICorDebugILFrame::GetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="1fb86-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="1fb86-103">命令ポインターの値と、命令ポインターの値がどのように取得されたかを記述するビットごとの組み合わせ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="1fb86-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fb86-104">構文</span><span class="sxs-lookup"><span data-stu-id="1fb86-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fb86-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1fb86-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="1fb86-106">[アウト]命令ポインターの値。</span><span class="sxs-lookup"><span data-stu-id="1fb86-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="1fb86-107">[アウト]命令ポインターの値が取得された方法を記述する、CorDebugMappingResult 列挙値のビットごとの組み合わせへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1fb86-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fb86-108">解説</span><span class="sxs-lookup"><span data-stu-id="1fb86-108">Remarks</span></span>  
 <span data-ttu-id="1fb86-109">命令ポインターの値は、スタック フレームの関数の Microsoft 中間言語 (MSIL) コードへのオフセットです。</span><span class="sxs-lookup"><span data-stu-id="1fb86-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="1fb86-110">スタック フレームがアクティブな場合、このアドレスが次に実行される命令になります。</span><span class="sxs-lookup"><span data-stu-id="1fb86-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="1fb86-111">スタック フレームがアクティブでない場合、このアドレスはスタック フレームが再アクティブ化されたときに実行される次の命令です。</span><span class="sxs-lookup"><span data-stu-id="1fb86-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="1fb86-112">このフレームがジャスト イン タイム (JIT) コンパイルされたフレームの場合、命令ポインターの値は実際のネイティブ命令ポインターから逆方向にマッピングすることによって決定されるため、値は概算値に過ぎない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1fb86-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fb86-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="1fb86-113">Requirements</span></span>  
 <span data-ttu-id="1fb86-114">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fb86-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fb86-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fb86-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fb86-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fb86-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fb86-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fb86-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
