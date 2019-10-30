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
ms.openlocfilehash: fdca03b781e07b709cbc54e673dbaa2a1130fbe3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135147"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a><span data-ttu-id="3ac65-102">ICLRStrongName::StrongNameCompareAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="3ac65-102">ICLRStrongName::StrongNameCompareAssemblies Method</span></span>
<span data-ttu-id="3ac65-103">厳密な名前の署名に基づいて 2 つのアセンブリが異なるかどうかが判定されます。</span><span class="sxs-lookup"><span data-stu-id="3ac65-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ac65-104">構文</span><span class="sxs-lookup"><span data-stu-id="3ac65-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ac65-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3ac65-105">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="3ac65-106">から最初のアセンブリへのパス。</span><span class="sxs-lookup"><span data-stu-id="3ac65-106">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="3ac65-107">から2番目のアセンブリへのパス。</span><span class="sxs-lookup"><span data-stu-id="3ac65-107">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="3ac65-108">入出力次のいずれかの値です。</span><span class="sxs-lookup"><span data-stu-id="3ac65-108">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="3ac65-109">`SN_CMP_DIFFERENT` (0)-アセンブリに異なるデータが含まれることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ac65-109">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="3ac65-110">`SN_CMP_IDENTICAL` (1)-署名やチェックサムなど、アセンブリがまったく同じであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ac65-110">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="3ac65-111">`SN_CMP_SIGONLY` (2)-アセンブリが署名とチェックサムのみで異なることを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ac65-111">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ac65-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="3ac65-112">Return Value</span></span>  
 <span data-ttu-id="3ac65-113">メソッドが正常に完了した場合は `S_OK`。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](https://go.microsoft.com/fwlink/?LinkId=213878)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3ac65-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ac65-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="3ac65-114">Requirements</span></span>  
 <span data-ttu-id="3ac65-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ac65-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ac65-116">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="3ac65-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3ac65-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3ac65-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ac65-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ac65-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ac65-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="3ac65-119">Remarks</span></span>  
 <span data-ttu-id="3ac65-120">アセンブリの厳密な名前の署名は、アセンブリのテキスト名、バージョン、カルチャ、および公開キートークンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3ac65-120">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac65-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ac65-121">See also</span></span>

- [<span data-ttu-id="3ac65-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3ac65-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
