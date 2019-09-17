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
ms.openlocfilehash: b0c2e8e46c7bb3a5e693c9ea16e6c5a0722b1898
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799151"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="f1a5d-102">StrongNameCompareAssemblies 関数</span><span class="sxs-lookup"><span data-stu-id="f1a5d-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="f1a5d-103">厳密な名前の署名に基づいて 2 つのアセンブリが異なるかどうかが判定されます。</span><span class="sxs-lookup"><span data-stu-id="f1a5d-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="f1a5d-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="f1a5d-104">This function has been deprecated.</span></span> <span data-ttu-id="f1a5d-105">代わりに[ICLRStrongName:: StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="f1a5d-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1a5d-106">構文</span><span class="sxs-lookup"><span data-stu-id="f1a5d-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1a5d-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1a5d-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="f1a5d-108">から最初のアセンブリへのパス。</span><span class="sxs-lookup"><span data-stu-id="f1a5d-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="f1a5d-109">から2番目のアセンブリへのパス。</span><span class="sxs-lookup"><span data-stu-id="f1a5d-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="f1a5d-110">入出力次のいずれかの値です。</span><span class="sxs-lookup"><span data-stu-id="f1a5d-110">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="f1a5d-111">`SN_CMP_DIFFERENT`(0)-アセンブリに異なるデータが含まれることを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1a5d-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="f1a5d-112">`SN_CMP_IDENTICAL`(1)-署名やチェックサムなど、アセンブリがまったく同じであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1a5d-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="f1a5d-113">`SN_CMP_SIGONLY`(2)-アセンブリが署名とチェックサムのみで異なることを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1a5d-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1a5d-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="f1a5d-114">Return Value</span></span>  
 <span data-ttu-id="f1a5d-115">`true`正常に完了した場合は。それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="f1a5d-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1a5d-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="f1a5d-116">Requirements</span></span>  
 <span data-ttu-id="f1a5d-117">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1a5d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1a5d-118">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="f1a5d-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f1a5d-119">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="f1a5d-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1a5d-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1a5d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1a5d-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1a5d-121">Remarks</span></span>  
 <span data-ttu-id="f1a5d-122">アセンブリの厳密な名前の署名は、アセンブリのテキスト名、バージョン、カルチャ、および公開キートークンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f1a5d-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="f1a5d-123">関数が正常に完了しない場合は、[StrongNameErrorInfo](strongnameerrorinfo-function.md) 関数を呼び出して、最後に生成されたエラーを取得します。`StrongNameCompareAssemblies`</span><span class="sxs-lookup"><span data-stu-id="f1a5d-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1a5d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1a5d-124">See also</span></span>

- [<span data-ttu-id="f1a5d-125">StrongNameCompareAssemblies メソッド</span><span class="sxs-lookup"><span data-stu-id="f1a5d-125">StrongNameCompareAssemblies Method</span></span>](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="f1a5d-126">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1a5d-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
