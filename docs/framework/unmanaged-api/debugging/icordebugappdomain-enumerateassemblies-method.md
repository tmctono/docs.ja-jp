---
title: ICorDebugAppDomain::EnumerateAssemblies メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateAssemblies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateAssemblies
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateAssemblies method [.NET Framework debugging]
- EnumerateAssemblies method [.NET Framework debugging]
ms.assetid: 7add64f9-19a8-46a9-be62-905d5e7d1bd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bacd93baae3f0c0b70c4b910e8130551b4f3e48
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738050"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="7b304-102">ICorDebugAppDomain::EnumerateAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="7b304-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="7b304-103">アプリケーション ドメインでアセンブリの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="7b304-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b304-104">構文</span><span class="sxs-lookup"><span data-stu-id="7b304-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b304-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7b304-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="7b304-106">[out]アプリケーション ドメイン内のアセンブリの列挙子である ICorDebugAssemblyEnum オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7b304-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b304-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="7b304-107">Requirements</span></span>  
 <span data-ttu-id="7b304-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b304-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b304-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b304-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b304-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b304-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b304-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b304-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
