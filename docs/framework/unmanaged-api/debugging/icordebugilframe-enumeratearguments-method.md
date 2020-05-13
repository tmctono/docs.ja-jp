---
title: ICorDebugILFrame::EnumerateArguments メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
ms.openlocfilehash: 3945b1dea62dc0616d669356faf60f0d09cfb084
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210307"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="6a9b9-102">ICorDebugILFrame::EnumerateArguments メソッド</span><span class="sxs-lookup"><span data-stu-id="6a9b9-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="6a9b9-103">このフレーム内の引数の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a9b9-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a9b9-104">構文</span><span class="sxs-lookup"><span data-stu-id="6a9b9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a9b9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6a9b9-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="6a9b9-106">入出力このフレーム内の引数の列挙子である、の各オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6a9b9-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a9b9-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="6a9b9-107">Remarks</span></span>  
 <span data-ttu-id="6a9b9-108">`EnumerateArguments`このテキストボックスオブジェクトで表される呼び出しフレームで使用可能な引数を一覧表示できる列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a9b9-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="6a9b9-109">この一覧には、 [vararg](/cpp/windows/vararg)である引数 (可変個の引数) と、ではない引数が含まれ `vararg` ます。</span><span class="sxs-lookup"><span data-stu-id="6a9b9-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a9b9-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="6a9b9-110">Requirements</span></span>  
 <span data-ttu-id="6a9b9-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9b9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a9b9-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a9b9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a9b9-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a9b9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a9b9-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a9b9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
