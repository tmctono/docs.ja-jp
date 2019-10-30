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
ms.openlocfilehash: 573b08fcf2ce0fa5ce3187df6ae6a1c2cc385f52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134004"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="00c58-102">ICorDebugAppDomain::EnumerateAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="00c58-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="00c58-103">アプリケーションドメイン内のアセンブリの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="00c58-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00c58-104">構文</span><span class="sxs-lookup"><span data-stu-id="00c58-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00c58-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="00c58-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="00c58-106">入出力アプリケーションドメイン内のアセンブリの列挙子である、の各オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="00c58-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00c58-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="00c58-107">Requirements</span></span>  
 <span data-ttu-id="00c58-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00c58-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00c58-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00c58-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00c58-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00c58-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00c58-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00c58-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
