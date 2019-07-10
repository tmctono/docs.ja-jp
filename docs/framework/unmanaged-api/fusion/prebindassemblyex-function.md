---
title: PreBindAssemblyEx 関数
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a23d3c4fd8eef2e361abf1602157cb4fbb820b48
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773862"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="3c4fb-102">PreBindAssemblyEx 関数</span><span class="sxs-lookup"><span data-stu-id="3c4fb-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="3c4fb-103">アセンブリのポリシー適用後の表示名を取得します。</span><span class="sxs-lookup"><span data-stu-id="3c4fb-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="3c4fb-104">この関数は、.NET Framework インフラストラクチャをサポートし、コードから直接使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="3c4fb-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c4fb-105">構文</span><span class="sxs-lookup"><span data-stu-id="3c4fb-105">Syntax</span></span>  
  
```cpp  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c4fb-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c4fb-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="3c4fb-107">[in]アプリケーションのコンテキストを識別します。</span><span class="sxs-lookup"><span data-stu-id="3c4fb-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="3c4fb-108">[in]アセンブリ名を識別します。</span><span class="sxs-lookup"><span data-stu-id="3c4fb-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="3c4fb-109">[in]親アセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="3c4fb-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="3c4fb-110">このパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="3c4fb-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="3c4fb-111">[in]ランタイムのバージョンを識別します。</span><span class="sxs-lookup"><span data-stu-id="3c4fb-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="3c4fb-112">[out]後のポリシーの表示名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c4fb-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="3c4fb-113">[入力] 将来の機能拡張に備えて予約されています。</span><span class="sxs-lookup"><span data-stu-id="3c4fb-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="3c4fb-114">`pvReserved` null 参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c4fb-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c4fb-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="3c4fb-115">Remarks</span></span>  
 <span data-ttu-id="3c4fb-116">`ppNamePostPolicy`関数が HRESULT FUSION_E_REF_DEF_MISMATCH を返す場合にのみ、出力パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="3c4fb-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="3c4fb-117">それ以外の場合、これが null です。</span><span class="sxs-lookup"><span data-stu-id="3c4fb-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c4fb-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="3c4fb-118">Requirements</span></span>  
 <span data-ttu-id="3c4fb-119">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c4fb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c4fb-120">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="3c4fb-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3c4fb-121">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="3c4fb-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c4fb-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c4fb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c4fb-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c4fb-123">See also</span></span>

- [<span data-ttu-id="3c4fb-124">Fusion グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="3c4fb-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
