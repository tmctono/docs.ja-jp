---
title: ICorDebugFrame::GetCode メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCode
helpviewer_keywords:
- GetCode method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCode method [.NET Framework debugging]
ms.assetid: fbaa0794-a031-4015-8beb-2749e47ac340
topic_type:
- apiref
ms.openlocfilehash: c8914ba1090ec5fd6540e9ead302675cb44f37e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208604"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="c3ede-102">ICorDebugFrame::GetCode メソッド</span><span class="sxs-lookup"><span data-stu-id="c3ede-102">ICorDebugFrame::GetCode Method</span></span>
<span data-ttu-id="c3ede-103">このスタックフレームに関連付けられているコードへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="c3ede-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3ede-104">構文</span><span class="sxs-lookup"><span data-stu-id="c3ede-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3ede-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3ede-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="c3ede-106">入出力このフレームに関連付けられているコードを表す、コードオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c3ede-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3ede-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="c3ede-107">Requirements</span></span>  
 <span data-ttu-id="c3ede-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3ede-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3ede-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3ede-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3ede-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3ede-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3ede-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3ede-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
