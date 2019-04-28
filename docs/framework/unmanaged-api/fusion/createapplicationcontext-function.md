---
title: CreateApplicationContext 関数
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d98829b29100824e5d606e23aaf287c9f6e81d69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771918"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="2aaf0-102">CreateApplicationContext 関数</span><span class="sxs-lookup"><span data-stu-id="2aaf0-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="2aaf0-103">この関数は、.NET Framework インフラストラクチャをサポートし、コードから直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="2aaf0-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aaf0-104">構文</span><span class="sxs-lookup"><span data-stu-id="2aaf0-104">Syntax</span></span>  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2aaf0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2aaf0-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="2aaf0-106">[in]フレンドリ名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2aaf0-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="2aaf0-107">[out]アプリケーションのコンテキストへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2aaf0-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aaf0-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="2aaf0-108">Requirements</span></span>  
 <span data-ttu-id="2aaf0-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2aaf0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aaf0-110">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="2aaf0-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2aaf0-111">**ライブラリ:** Fusion.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="2aaf0-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="2aaf0-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aaf0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aaf0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2aaf0-113">See also</span></span>

- [<span data-ttu-id="2aaf0-114">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2aaf0-114">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="2aaf0-115">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="2aaf0-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="2aaf0-116">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="2aaf0-116">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
