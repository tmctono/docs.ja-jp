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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a7b8985e7580282d0e38205f9b1d6078f86cee6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988612"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="5fd94-102">ICorDebugILFrame::GetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="5fd94-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="5fd94-103">命令ポインターの値と命令ポインターの値の取得方法を示すビットごとの組み合わせ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5fd94-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fd94-104">構文</span><span class="sxs-lookup"><span data-stu-id="5fd94-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fd94-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5fd94-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="5fd94-106">[out]命令ポインターの値。</span><span class="sxs-lookup"><span data-stu-id="5fd94-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="5fd94-107">[out]命令ポインターの値の取得方法を説明する CorDebugMappingResult 列挙値のビットごとの組み合わせへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5fd94-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fd94-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="5fd94-108">Remarks</span></span>  
 <span data-ttu-id="5fd94-109">命令ポインターの値は、関数の Microsoft intermediate language (MSIL) コードにスタック フレームのオフセットです。</span><span class="sxs-lookup"><span data-stu-id="5fd94-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="5fd94-110">スタック フレームがアクティブな場合は、このアドレスは次の命令を実行するには。</span><span class="sxs-lookup"><span data-stu-id="5fd94-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="5fd94-111">スタック フレームがアクティブでない場合、このアドレスは、スタック フレームが再アクティブ化したときに実行するには、次の命令は。</span><span class="sxs-lookup"><span data-stu-id="5fd94-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="5fd94-112">このフレームが・ イン タイム (JIT) コンパイルされたフレームの場合は、命令ポインターの値は値が概数のみであるため、実際のネイティブ命令ポインターから旧バージョンとのマッピングで決定します。</span><span class="sxs-lookup"><span data-stu-id="5fd94-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fd94-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="5fd94-113">Requirements</span></span>  
 <span data-ttu-id="5fd94-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fd94-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fd94-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fd94-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fd94-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fd94-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fd94-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fd94-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
