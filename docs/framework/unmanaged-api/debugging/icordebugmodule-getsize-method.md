---
title: ICorDebugModule::GetSize メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 540288f83de9c3c6ff2111330c77ded48abd6d5f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761664"
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="50b50-102">ICorDebugModule::GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="50b50-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="50b50-103">モジュールのバイト単位のサイズを取得します。</span><span class="sxs-lookup"><span data-stu-id="50b50-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50b50-104">構文</span><span class="sxs-lookup"><span data-stu-id="50b50-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50b50-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="50b50-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="50b50-106">[out]\(バイト単位)、モジュールのサイズ。</span><span class="sxs-lookup"><span data-stu-id="50b50-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="50b50-107">モジュールは、ネイティブ イメージ ジェネレーター (NGen.exe) から生成された、モジュールのサイズが 0 になります。</span><span class="sxs-lookup"><span data-stu-id="50b50-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50b50-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="50b50-108">Requirements</span></span>  
 <span data-ttu-id="50b50-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="50b50-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50b50-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50b50-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50b50-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50b50-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50b50-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50b50-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
