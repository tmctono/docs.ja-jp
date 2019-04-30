---
title: StrongNameKeyGenEx 関数
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af75a645b11325b96740807f9a3df65f5a676026
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000247"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="bc0c1-102">StrongNameKeyGenEx 関数</span><span class="sxs-lookup"><span data-stu-id="bc0c1-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="bc0c1-103">指定されたキー サイズ、厳密な名前を使用して新しい公開/秘密キー ペアを生成します。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="bc0c1-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-104">This function has been deprecated.</span></span> <span data-ttu-id="bc0c1-105">使用して、 [iclrstrongname::strongnamekeygenex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc0c1-106">構文</span><span class="sxs-lookup"><span data-stu-id="bc0c1-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc0c1-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bc0c1-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="bc0c1-108">[in]要求されたキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-108">[in] The requested key container name.</span></span> <span data-ttu-id="bc0c1-109">`wszKeyContainer` 空でない文字列であるか、一時テーブル名を生成する場合は null が必要です。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="bc0c1-110">[in]登録されているキーのままにするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="bc0c1-111">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="bc0c1-112">0x00000000 の際に使用される`wszKeyContainer`一時的なキー コンテナーの名前を生成する場合は null です。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="bc0c1-113">0x00000001 (`SN_LEAVE_KEY`) のキーを左に登録する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="bc0c1-114">[in]ビット単位で、キーの要求されたサイズ。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="bc0c1-115">[out]返された公開/秘密キー ペア。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="bc0c1-116">[out]サイズ (バイト単位) の`ppbKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc0c1-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="bc0c1-117">Return Value</span></span>  
 <span data-ttu-id="bc0c1-118">`true` 正常に終了します。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc0c1-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="bc0c1-119">Remarks</span></span>  
 <span data-ttu-id="bc0c1-120">.NET Framework バージョン 1.0 および 1.1 が必要です、 `dwKeySize` version 2.0 を 1024 ビットです。 厳密な名前でアセンブリに署名するには、2048 ビットのキーのサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="bc0c1-121">呼び出す必要があります、キーが取得された後、 [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)割り当てられたメモリを解放する関数。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="bc0c1-122">場合、`StrongNameKeyGenEx`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc0c1-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="bc0c1-123">Requirements</span></span>  
 <span data-ttu-id="bc0c1-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc0c1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc0c1-125">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="bc0c1-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bc0c1-126">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="bc0c1-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc0c1-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc0c1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc0c1-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc0c1-128">See also</span></span>

- [<span data-ttu-id="bc0c1-129">StrongNameKeyGenEx メソッド</span><span class="sxs-lookup"><span data-stu-id="bc0c1-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="bc0c1-130">StrongNameKeyGen メソッド</span><span class="sxs-lookup"><span data-stu-id="bc0c1-130">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="bc0c1-131">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bc0c1-131">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
