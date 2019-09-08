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
ms.openlocfilehash: 25364330dafdf858c4b41e9a05731c37e97fbb57
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795436"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="c603b-102">CreateApplicationContext 関数</span><span class="sxs-lookup"><span data-stu-id="c603b-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="c603b-103">この関数は、.NET Framework インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="c603b-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c603b-104">構文</span><span class="sxs-lookup"><span data-stu-id="c603b-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="c603b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c603b-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="c603b-106">からフレンドリ名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c603b-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="c603b-107">入出力アプリケーションコンテキストへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c603b-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c603b-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="c603b-108">Requirements</span></span>  
 <span data-ttu-id="c603b-109">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c603b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c603b-110">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="c603b-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c603b-111">**ライブラリ**Fusion にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c603b-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="c603b-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c603b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c603b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c603b-113">See also</span></span>

- [<span data-ttu-id="c603b-114">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c603b-114">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="c603b-115">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="c603b-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="c603b-116">グローバル アセンブリ キャッシュ</span><span class="sxs-lookup"><span data-stu-id="c603b-116">Global Assembly Cache</span></span>](../../app-domains/gac.md)
