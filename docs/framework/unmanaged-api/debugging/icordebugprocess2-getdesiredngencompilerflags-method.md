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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a59067f72005e87152680e4f990fc74e4acdaa9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948929"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="fdaad-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="fdaad-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="fdaad-103">現在のコンパイラの共通言語ランタイム (CLR) を使用して、正しいをプリコンパイルするフラグの設定を取得します (つまり、ネイティブ) このプロセスに読み込まれるイメージ。</span><span class="sxs-lookup"><span data-stu-id="fdaad-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdaad-104">構文</span><span class="sxs-lookup"><span data-stu-id="fdaad-104">Syntax</span></span>  
  
```  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdaad-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fdaad-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="fdaad-106">[out]ビットごとの組み合わせへのポインター、 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)ロードする適切なプリコンパイル済みのイメージの選択に使用する列挙値。</span><span class="sxs-lookup"><span data-stu-id="fdaad-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdaad-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="fdaad-107">Remarks</span></span>  
 <span data-ttu-id="fdaad-108">使用して、 [icordebugprocess 2::setdesiredngencompilerflags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) CLR が読み込みに適切なコンパイル済みのイメージを選択に使用するフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="fdaad-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdaad-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="fdaad-109">Requirements</span></span>  
 <span data-ttu-id="fdaad-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdaad-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdaad-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdaad-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdaad-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdaad-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdaad-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdaad-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
