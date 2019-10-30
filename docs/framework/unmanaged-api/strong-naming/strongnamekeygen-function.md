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
ms.openlocfilehash: 79b2235e3645c89c2cd9ebcce079d5eb7efdd162
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128739"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="de418-102">StrongNameKeyGen 関数</span><span class="sxs-lookup"><span data-stu-id="de418-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="de418-103">厳密な名前を使用するために新しい公開/秘密キーの組が作成されます。</span><span class="sxs-lookup"><span data-stu-id="de418-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="de418-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="de418-104">This function has been deprecated.</span></span> <span data-ttu-id="de418-105">代わりに[ICLRStrongName:: StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="de418-105">Use the [ICLRStrongName::StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de418-106">構文</span><span class="sxs-lookup"><span data-stu-id="de418-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de418-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de418-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="de418-108">から要求されたキーコンテナー名。</span><span class="sxs-lookup"><span data-stu-id="de418-108">[in] The requested key container name.</span></span> <span data-ttu-id="de418-109">`wszKeyContainer` は、空でない文字列であるか、または一時名を生成するために null である必要があります。</span><span class="sxs-lookup"><span data-stu-id="de418-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="de418-110">からキーを登録したままにするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="de418-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="de418-111">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="de418-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="de418-112">0x00000000-一時キーコンテナー名を生成するために `wszKeyContainer` が null の場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="de418-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="de418-113">0x00000001 (`SN_LEAVE_KEY`)-キーを登録したままにすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="de418-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="de418-114">入出力返された公開/秘密キーのペア。</span><span class="sxs-lookup"><span data-stu-id="de418-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="de418-115">入出力`ppbKeyBlob`のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="de418-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de418-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="de418-116">Return Value</span></span>  
 <span data-ttu-id="de418-117">正常に完了した場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="de418-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de418-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="de418-118">Remarks</span></span>  
 <span data-ttu-id="de418-119">`StrongNameKeyGen` 関数は、1024ビットのキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="de418-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="de418-120">キーが取得されたら、 [StrongNameFreeBuffer](strongnamefreebuffer-function.md)関数を呼び出して、割り当てられたメモリを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de418-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="de418-121">`StrongNameKeyGen` 関数が正常に完了しない場合は、 [StrongNameErrorInfo](strongnameerrorinfo-function.md)関数を呼び出して、最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="de418-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de418-122">［要件］</span><span class="sxs-lookup"><span data-stu-id="de418-122">Requirements</span></span>  
 <span data-ttu-id="de418-123">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de418-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de418-124">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="de418-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="de418-125">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="de418-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="de418-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de418-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de418-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="de418-127">See also</span></span>

- [<span data-ttu-id="de418-128">StrongNameKeyGen メソッド</span><span class="sxs-lookup"><span data-stu-id="de418-128">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="de418-129">StrongNameKeyGenEx メソッド</span><span class="sxs-lookup"><span data-stu-id="de418-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="de418-130">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="de418-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
