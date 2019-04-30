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
ms.openlocfilehash: 6ce95daaee3c74ac57b107ab8bcb23d41e42cabb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989541"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="38e17-102">ICorDebugAppDomain::EnumerateAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="38e17-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="38e17-103">アプリケーション ドメインでアセンブリの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="38e17-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38e17-104">構文</span><span class="sxs-lookup"><span data-stu-id="38e17-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38e17-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="38e17-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="38e17-106">[out]アプリケーション ドメイン内のアセンブリの列挙子である ICorDebugAssemblyEnum オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="38e17-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38e17-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="38e17-107">Requirements</span></span>  
 <span data-ttu-id="38e17-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38e17-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38e17-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38e17-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38e17-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38e17-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38e17-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38e17-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
