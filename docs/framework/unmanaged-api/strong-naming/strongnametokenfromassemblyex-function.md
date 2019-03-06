---
title: StrongNameTokenFromAssemblyEx 関数
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f95ac4e4c21a2cbaab9f91c1257a868bdce65af
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499187"
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="c3ddb-102">StrongNameTokenFromAssemblyEx 関数</span><span class="sxs-lookup"><span data-stu-id="c3ddb-102">StrongNameTokenFromAssemblyEx Function</span></span>
<span data-ttu-id="c3ddb-103">指定したアセンブリ ファイルから厳密な名前トークンを作成し、トークンが表す公開キーを返します。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="c3ddb-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-104">This function has been deprecated.</span></span> <span data-ttu-id="c3ddb-105">使用して、 [iclrstrongname::strongnametokenfromassemblyex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3ddb-106">構文</span><span class="sxs-lookup"><span data-stu-id="c3ddb-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3ddb-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3ddb-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c3ddb-108">[in]アセンブリのポータブル実行可能 (PE) ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="c3ddb-109">[out]厳密な名前が返されたトークンです。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="c3ddb-110">[out]厳密な名前トークンのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="c3ddb-111">[out]返される公開キー。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="c3ddb-112">[out]公開キーのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3ddb-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="c3ddb-113">Return Value</span></span>  
 <span data-ttu-id="c3ddb-114">`true` 正常に終了します。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3ddb-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="c3ddb-115">Remarks</span></span>  
 <span data-ttu-id="c3ddb-116">厳密な名前トークンは、公開キーの短縮形です。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="c3ddb-117">トークンは、アセンブリの署名に使用する公開キーから作成される 64 ビット ハッシュです。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="c3ddb-118">トークンは、アセンブリの厳密な名前の一部であるし、アセンブリのメタデータから読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="c3ddb-119">呼び出す必要があります、キーを取得し、トークンを作成、後に、 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)割り当てられたメモリを解放する関数。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="c3ddb-120">場合、`StrongNameTokenFromAssemblyEx`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3ddb-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="c3ddb-121">Requirements</span></span>  
 <span data-ttu-id="c3ddb-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3ddb-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3ddb-123">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="c3ddb-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c3ddb-124">**ライブラリ:** Mscoree.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="c3ddb-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="c3ddb-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3ddb-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ddb-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3ddb-126">See also</span></span>
- [<span data-ttu-id="c3ddb-127">StrongNameTokenFromAssemblyEx メソッド</span><span class="sxs-lookup"><span data-stu-id="c3ddb-127">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="c3ddb-128">StrongNameTokenFromAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="c3ddb-128">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="c3ddb-129">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3ddb-129">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
