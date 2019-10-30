---
title: ICorDebugProcess2::GetDesiredNGENCompilerFlags メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
ms.openlocfilehash: 2d5b07acb9dc374fdd8872ed982a92171da28603
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137233"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="b65db-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="b65db-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="b65db-103">このプロセスに読み込まれる正しいプリコンパイル済み (ネイティブ) イメージを選択するために共通言語ランタイム (CLR) が使用する、現在のコンパイラフラグ設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="b65db-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b65db-104">構文</span><span class="sxs-lookup"><span data-stu-id="b65db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b65db-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b65db-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="b65db-106">入出力読み込まれる正しいプリコンパイル済みイメージを選択するために使用される、 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)列挙値のビットごとの組み合わせへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b65db-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b65db-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b65db-107">Remarks</span></span>  
 <span data-ttu-id="b65db-108">[ICorDebugProcess2:: SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)メソッドを使用して、読み込む適切なプリコンパイル済みイメージを選択するために CLR が使用するフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="b65db-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b65db-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="b65db-109">Requirements</span></span>  
 <span data-ttu-id="b65db-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b65db-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b65db-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b65db-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b65db-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b65db-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b65db-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b65db-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
