---
title: StrongNameKeyGen 関数
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8ebecce4078ba6c2b59e6bfba2d54300ba0c4ee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107381"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="0743c-102">StrongNameKeyGen 関数</span><span class="sxs-lookup"><span data-stu-id="0743c-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="0743c-103">厳密な名前を使用するために新しい公開/秘密キーの組が作成されます。</span><span class="sxs-lookup"><span data-stu-id="0743c-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="0743c-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="0743c-104">This function has been deprecated.</span></span> <span data-ttu-id="0743c-105">使用して、 [iclrstrongname::strongnamekeygen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="0743c-105">Use the [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0743c-106">構文</span><span class="sxs-lookup"><span data-stu-id="0743c-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0743c-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0743c-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="0743c-108">[in]要求されたキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="0743c-108">[in] The requested key container name.</span></span> <span data-ttu-id="0743c-109">`wszKeyContainer` 空でない文字列であるか、一時テーブル名を生成する場合は null が必要です。</span><span class="sxs-lookup"><span data-stu-id="0743c-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0743c-110">[in]登録されているキーのままにするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0743c-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="0743c-111">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0743c-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="0743c-112">0x00000000 の際に使用される`wszKeyContainer`一時的なキー コンテナーの名前を生成する場合は null です。</span><span class="sxs-lookup"><span data-stu-id="0743c-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="0743c-113">0x00000001 (`SN_LEAVE_KEY`) のキーを左に登録する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="0743c-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="0743c-114">[out]返された公開/秘密キー ペア。</span><span class="sxs-lookup"><span data-stu-id="0743c-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="0743c-115">[out]サイズ (バイト単位) の`ppbKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="0743c-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0743c-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="0743c-116">Return Value</span></span>  
 <span data-ttu-id="0743c-117">`true` 正常に終了します。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="0743c-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0743c-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="0743c-118">Remarks</span></span>  
 <span data-ttu-id="0743c-119">`StrongNameKeyGen`関数は、1024 ビットのキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0743c-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="0743c-120">呼び出す必要があります、キーが取得された後、 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)割り当てられたメモリを解放する関数。</span><span class="sxs-lookup"><span data-stu-id="0743c-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="0743c-121">場合、`StrongNameKeyGen`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="0743c-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0743c-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="0743c-122">Requirements</span></span>  
 <span data-ttu-id="0743c-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0743c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0743c-124">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="0743c-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0743c-125">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="0743c-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0743c-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0743c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0743c-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="0743c-127">See also</span></span>

- [<span data-ttu-id="0743c-128">StrongNameKeyGen メソッド</span><span class="sxs-lookup"><span data-stu-id="0743c-128">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="0743c-129">StrongNameKeyGenEx メソッド</span><span class="sxs-lookup"><span data-stu-id="0743c-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="0743c-130">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0743c-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
