---
title: ICLRStrongName::StrongNameCompareAssemblies メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 266e2d92ea3c21a9df28bda18a5d0f32e5a32090
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748093"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="28bf4-102">ICLRStrongName::StrongNameCompareAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="28bf4-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="28bf4-103">厳密な名前の署名に基づいて 2 つのアセンブリが異なるかどうかが判定されます。</span><span class="sxs-lookup"><span data-stu-id="28bf4-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28bf4-104">構文</span><span class="sxs-lookup"><span data-stu-id="28bf4-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28bf4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="28bf4-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="28bf4-106">[in]最初のアセンブリへのパス。</span><span class="sxs-lookup"><span data-stu-id="28bf4-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="28bf4-107">[in]2 つ目のアセンブリへのパス。</span><span class="sxs-lookup"><span data-stu-id="28bf4-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="28bf4-108">[out]次の値のいずれか:</span><span class="sxs-lookup"><span data-stu-id="28bf4-108">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="28bf4-109">`SN_CMP_DIFFERENT` (0) のアセンブリが別のデータを含むことを指定します。</span><span class="sxs-lookup"><span data-stu-id="28bf4-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="28bf4-110">`SN_CMP_IDENTICAL` (1) - アセンブリが、署名とチェックサムも含めて一致ではことを指定します。</span><span class="sxs-lookup"><span data-stu-id="28bf4-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="28bf4-111">`SN_CMP_SIGONLY` (2) のアセンブリが署名とチェックサムによってのみが異なることを指定します。</span><span class="sxs-lookup"><span data-stu-id="28bf4-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28bf4-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="28bf4-112">Return Value</span></span>  
 <span data-ttu-id="28bf4-113">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="28bf4-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28bf4-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="28bf4-114">Requirements</span></span>  
 <span data-ttu-id="28bf4-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="28bf4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28bf4-116">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="28bf4-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="28bf4-117">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="28bf4-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28bf4-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28bf4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28bf4-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="28bf4-119">Remarks</span></span>  
 <span data-ttu-id="28bf4-120">アセンブリの厳密な名前の署名は、アセンブリのテキスト名、バージョン、カルチャ、および公開キー トークンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="28bf4-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28bf4-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="28bf4-121">See also</span></span>

- [<span data-ttu-id="28bf4-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="28bf4-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
