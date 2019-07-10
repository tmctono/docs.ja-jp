---
title: StrongNameCompareAssemblies 関数
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3693a42db8e32a4bb7a399f8c930da011130893
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778727"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="7608e-102">StrongNameCompareAssemblies 関数</span><span class="sxs-lookup"><span data-stu-id="7608e-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="7608e-103">厳密な名前の署名に基づいて 2 つのアセンブリが異なるかどうかが判定されます。</span><span class="sxs-lookup"><span data-stu-id="7608e-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="7608e-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="7608e-104">This function has been deprecated.</span></span> <span data-ttu-id="7608e-105">使用して、 [iclrstrongname::strongnamecompareassemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="7608e-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7608e-106">構文</span><span class="sxs-lookup"><span data-stu-id="7608e-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7608e-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7608e-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="7608e-108">[in]最初のアセンブリへのパス。</span><span class="sxs-lookup"><span data-stu-id="7608e-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="7608e-109">[in]2 つ目のアセンブリへのパス。</span><span class="sxs-lookup"><span data-stu-id="7608e-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="7608e-110">[out]次の値のいずれか:</span><span class="sxs-lookup"><span data-stu-id="7608e-110">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="7608e-111">`SN_CMP_DIFFERENT` (0) のアセンブリが別のデータを含むことを指定します。</span><span class="sxs-lookup"><span data-stu-id="7608e-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="7608e-112">`SN_CMP_IDENTICAL` (1) - アセンブリが、署名とチェックサムも含めて一致ではことを指定します。</span><span class="sxs-lookup"><span data-stu-id="7608e-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="7608e-113">`SN_CMP_SIGONLY` (2) のアセンブリが署名とチェックサムによってのみが異なることを指定します。</span><span class="sxs-lookup"><span data-stu-id="7608e-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7608e-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="7608e-114">Return Value</span></span>  
 <span data-ttu-id="7608e-115">`true` 正常に終了します。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="7608e-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7608e-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="7608e-116">Requirements</span></span>  
 <span data-ttu-id="7608e-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7608e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7608e-118">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="7608e-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7608e-119">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="7608e-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7608e-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7608e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7608e-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="7608e-121">Remarks</span></span>  
 <span data-ttu-id="7608e-122">アセンブリの厳密な名前の署名は、アセンブリのテキスト名、バージョン、カルチャ、および公開キー トークンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="7608e-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="7608e-123">場合、`StrongNameCompareAssemblies`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="7608e-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7608e-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="7608e-124">See also</span></span>

- [<span data-ttu-id="7608e-125">StrongNameCompareAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="7608e-125">StrongNameCompareAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="7608e-126">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7608e-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
