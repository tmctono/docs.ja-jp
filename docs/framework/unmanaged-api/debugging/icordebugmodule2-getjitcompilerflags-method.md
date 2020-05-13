---
title: ICorDebugModule2::GetJITCompilerFlags メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.GetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::GetJITCompilerFlags
helpviewer_keywords:
- GetJITCompilerFlags method [.NET Framework debugging]
- ICorDebugModule2::GetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: 7212d9f4-989b-44e3-b8d4-ffc35922f6a0
topic_type:
- apiref
ms.openlocfilehash: 6af5bc22616be196be7fdb0d417800d631d87506
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213648"
---
# <a name="icordebugmodule2getjitcompilerflags-method"></a><span data-ttu-id="0a87b-102">ICorDebugModule2::GetJITCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="0a87b-102">ICorDebugModule2::GetJITCompilerFlags Method</span></span>
<span data-ttu-id="0a87b-103">この ICorDebugModule2 の just-in-time (JIT) コンパイルを制御するフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="0a87b-103">Gets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a87b-104">構文</span><span class="sxs-lookup"><span data-stu-id="0a87b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJITCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a87b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0a87b-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="0a87b-106">入出力JIT コンパイルを制御する[CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md)列挙体の値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0a87b-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that controls the JIT compilation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a87b-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="0a87b-107">Requirements</span></span>  
 <span data-ttu-id="0a87b-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a87b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a87b-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a87b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a87b-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a87b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a87b-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a87b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
