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
ms.openlocfilehash: 63ddd90f3a8090853d10f03052915d10e1503ea6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125210"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="0763f-102">StrongNameKeyGenEx 関数</span><span class="sxs-lookup"><span data-stu-id="0763f-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="0763f-103">厳密な名前の使用のために、指定されたキーサイズを持つ新しい公開/秘密キーのペアを生成します。</span><span class="sxs-lookup"><span data-stu-id="0763f-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="0763f-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="0763f-104">This function has been deprecated.</span></span> <span data-ttu-id="0763f-105">代わりに[ICLRStrongName:: StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="0763f-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0763f-106">構文</span><span class="sxs-lookup"><span data-stu-id="0763f-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0763f-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0763f-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="0763f-108">から要求されたキーコンテナー名。</span><span class="sxs-lookup"><span data-stu-id="0763f-108">[in] The requested key container name.</span></span> <span data-ttu-id="0763f-109">`wszKeyContainer` は、空でない文字列であるか、または一時名を生成するために null である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0763f-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0763f-110">からキーを登録したままにするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0763f-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="0763f-111">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0763f-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="0763f-112">0x00000000-一時キーコンテナー名を生成するために `wszKeyContainer` が null の場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="0763f-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="0763f-113">0x00000001 (`SN_LEAVE_KEY`)-キーを登録したままにすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="0763f-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="0763f-114">から要求されたキーのサイズ (ビット単位)。</span><span class="sxs-lookup"><span data-stu-id="0763f-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="0763f-115">入出力返された公開/秘密キーのペア。</span><span class="sxs-lookup"><span data-stu-id="0763f-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="0763f-116">入出力`ppbKeyBlob`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="0763f-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0763f-117">戻り値</span><span class="sxs-lookup"><span data-stu-id="0763f-117">Return Value</span></span>  
 <span data-ttu-id="0763f-118">正常に完了した場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="0763f-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0763f-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="0763f-119">Remarks</span></span>  
 <span data-ttu-id="0763f-120">.NET Framework バージョン1.0 および1.1 では、厳密な名前でアセンブリに署名するには、1024ビットの `dwKeySize` が必要です。バージョン2.0 では、2048ビットキーのサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="0763f-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="0763f-121">キーが取得されたら、 [StrongNameFreeBuffer](strongnamefreebuffer-function.md)関数を呼び出して、割り当てられたメモリを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0763f-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="0763f-122">`StrongNameKeyGenEx` 関数が正常に完了しない場合は、 [StrongNameErrorInfo](strongnameerrorinfo-function.md)関数を呼び出して、最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="0763f-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0763f-123">［要件］</span><span class="sxs-lookup"><span data-stu-id="0763f-123">Requirements</span></span>  
 <span data-ttu-id="0763f-124">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0763f-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0763f-125">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="0763f-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0763f-126">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="0763f-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0763f-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0763f-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0763f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="0763f-128">See also</span></span>

- [<span data-ttu-id="0763f-129">StrongNameKeyGenEx メソッド</span><span class="sxs-lookup"><span data-stu-id="0763f-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="0763f-130">StrongNameKeyGen メソッド</span><span class="sxs-lookup"><span data-stu-id="0763f-130">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="0763f-131">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0763f-131">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
