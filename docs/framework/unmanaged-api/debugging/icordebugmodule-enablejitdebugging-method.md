---
title: ICorDebugModule::EnableJITDebugging メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableJITDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 642c4fd600d10ef89a08aa32bef5c8e7455552c7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473821"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="8709e-102">ICorDebugModule::EnableJITDebugging メソッド</span><span class="sxs-lookup"><span data-stu-id="8709e-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="8709e-103">ジャストイン タイム (JIT) コンパイラがこのモジュール内でメソッドのデバッグ情報を保持するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="8709e-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8709e-104">構文</span><span class="sxs-lookup"><span data-stu-id="8709e-104">Syntax</span></span>  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8709e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8709e-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="8709e-106">[in]この値に設定`true`Microsoft intermediate language (MSIL) のバージョンと、このモジュール内の各メソッドの JIT コンパイルされたバージョン間のマッピング情報を保持するために、JIT コンパイラを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8709e-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="8709e-107">[in]この値に設定`true`デバッグの特定の特定の JIT 最適化を使用したコードを生成する、JIT コンパイラを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8709e-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8709e-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="8709e-108">Remarks</span></span>  
 <span data-ttu-id="8709e-109">既定では、デバッガーがアクティブなときに読み込まれているすべてのモジュール、JIT デバッグを有効になっています。</span><span class="sxs-lookup"><span data-stu-id="8709e-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="8709e-110">プログラムでを有効または無効にするには、グローバル設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="8709e-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8709e-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="8709e-111">Requirements</span></span>  
 <span data-ttu-id="8709e-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8709e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8709e-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8709e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8709e-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8709e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8709e-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8709e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
