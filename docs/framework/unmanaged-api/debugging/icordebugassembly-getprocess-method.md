---
title: ICorDebugAssembly::GetProcess メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type:
- apiref
ms.openlocfilehash: 49b234b065eb66dc2ec0bc7e991117c5b54a92f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73196349"
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="1a8aa-102">ICorDebugAssembly::GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="1a8aa-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="1a8aa-103">このツールのアセンブリインスタンスが実行されているプロセスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a8aa-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a8aa-104">構文</span><span class="sxs-lookup"><span data-stu-id="1a8aa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a8aa-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1a8aa-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="1a8aa-106">入出力プロセスを表す、オブジェクトインターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1a8aa-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a8aa-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="1a8aa-107">Requirements</span></span>  
 <span data-ttu-id="1a8aa-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a8aa-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a8aa-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a8aa-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a8aa-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a8aa-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a8aa-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a8aa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
