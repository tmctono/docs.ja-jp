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
ms.openlocfilehash: 4d7eca3c2825707c9190436377bba7e4bb0d5447
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757976"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="15867-102">ICorDebugILFrame::GetIP メソッド</span><span class="sxs-lookup"><span data-stu-id="15867-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="15867-103">命令ポインターの値と命令ポインターの値の取得方法を示すビットごとの組み合わせ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="15867-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15867-104">構文</span><span class="sxs-lookup"><span data-stu-id="15867-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15867-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="15867-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="15867-106">[out]命令ポインターの値。</span><span class="sxs-lookup"><span data-stu-id="15867-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="15867-107">[out]命令ポインターの値の取得方法を説明する CorDebugMappingResult 列挙値のビットごとの組み合わせへのポインター。</span><span class="sxs-lookup"><span data-stu-id="15867-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15867-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="15867-108">Remarks</span></span>  
 <span data-ttu-id="15867-109">命令ポインターの値は、関数の Microsoft intermediate language (MSIL) コードにスタック フレームのオフセットです。</span><span class="sxs-lookup"><span data-stu-id="15867-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="15867-110">スタック フレームがアクティブな場合は、このアドレスは次の命令を実行するには。</span><span class="sxs-lookup"><span data-stu-id="15867-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="15867-111">スタック フレームがアクティブでない場合、このアドレスは、スタック フレームが再アクティブ化したときに実行するには、次の命令は。</span><span class="sxs-lookup"><span data-stu-id="15867-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="15867-112">このフレームが・ イン タイム (JIT) コンパイルされたフレームの場合は、命令ポインターの値は値が概数のみであるため、実際のネイティブ命令ポインターから旧バージョンとのマッピングで決定します。</span><span class="sxs-lookup"><span data-stu-id="15867-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15867-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="15867-113">Requirements</span></span>  
 <span data-ttu-id="15867-114">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="15867-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15867-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15867-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15867-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15867-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15867-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15867-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
