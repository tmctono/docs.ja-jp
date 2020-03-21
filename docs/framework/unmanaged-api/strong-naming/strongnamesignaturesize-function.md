---
title: StrongNameSignatureSize 関数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
ms.openlocfilehash: a19d875b8fb81f2af3821e69452f0f0ed591cd22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176891"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="19a2a-102">StrongNameSignatureSize 関数</span><span class="sxs-lookup"><span data-stu-id="19a2a-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="19a2a-103">厳密な名前の署名のサイズが返されます。</span><span class="sxs-lookup"><span data-stu-id="19a2a-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="19a2a-104">`StrongNameSignatureSize`通常は、遅延署名されたアセンブリを作成するときに、ファイルに確保する領域を決定するためにコンパイラによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="19a2a-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="19a2a-105">この関数は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="19a2a-105">This function has been deprecated.</span></span> <span data-ttu-id="19a2a-106">代わりに、メソッド[を](../hosting/iclrstrongname-strongnamesignaturesize-method.md)使用します。</span><span class="sxs-lookup"><span data-stu-id="19a2a-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19a2a-107">構文</span><span class="sxs-lookup"><span data-stu-id="19a2a-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="19a2a-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="19a2a-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="19a2a-109">[in]厳密な名前の署名を生成するために使用されるキー ペアのパブリック部分を含む[、型の PublicKeyBlob](publickeyblob-structure.md)の構造体。</span><span class="sxs-lookup"><span data-stu-id="19a2a-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="19a2a-110">[in]のサイズ (バイト単位)`pbPublicKeyBlob`です。</span><span class="sxs-lookup"><span data-stu-id="19a2a-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="19a2a-111">[in]厳密な名前の署名を格納するために必要なバイト数。</span><span class="sxs-lookup"><span data-stu-id="19a2a-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19a2a-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="19a2a-112">Return Value</span></span>  
 <span data-ttu-id="19a2a-113">`true`正常に完了した場合。それ以外`false`の場合は、 .</span><span class="sxs-lookup"><span data-stu-id="19a2a-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19a2a-114">解説</span><span class="sxs-lookup"><span data-stu-id="19a2a-114">Remarks</span></span>  
 <span data-ttu-id="19a2a-115">関数が`StrongNameSignatureSize`正常に完了しない場合は、[関数](strongnameerrorinfo-function.md)を呼び出して、最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="19a2a-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19a2a-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="19a2a-116">Requirements</span></span>  
 <span data-ttu-id="19a2a-117">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19a2a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19a2a-118">**ヘッダー:** ストロングネーム.h</span><span class="sxs-lookup"><span data-stu-id="19a2a-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="19a2a-119">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="19a2a-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="19a2a-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19a2a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19a2a-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="19a2a-121">See also</span></span>

- [<span data-ttu-id="19a2a-122">StrongNameSignatureSize メソッド</span><span class="sxs-lookup"><span data-stu-id="19a2a-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="19a2a-123">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="19a2a-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
