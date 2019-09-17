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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f98b971e430a2c35a4c484f4f9c4bf387c640c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798955"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="9135c-102">StrongNameSignatureSize 関数</span><span class="sxs-lookup"><span data-stu-id="9135c-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="9135c-103">厳密な名前の署名のサイズが返されます。</span><span class="sxs-lookup"><span data-stu-id="9135c-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="9135c-104">`StrongNameSignatureSize`は、通常、コンパイラによって使用され、遅延署名されたアセンブリを作成するときにファイルで予約する領域の量を決定します。</span><span class="sxs-lookup"><span data-stu-id="9135c-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="9135c-105">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="9135c-105">This function has been deprecated.</span></span> <span data-ttu-id="9135c-106">代わりに[ICLRStrongName:: StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="9135c-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9135c-107">構文</span><span class="sxs-lookup"><span data-stu-id="9135c-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="9135c-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9135c-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="9135c-109">から厳密な名前の署名を生成するために使用されるキーペアの公開部分を格納する[Publickeyblob](publickeyblob-structure.md)型の構造体。</span><span class="sxs-lookup"><span data-stu-id="9135c-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="9135c-110">からの`pbPublicKeyBlob`サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="9135c-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="9135c-111">から厳密な名前の署名を格納するために必要なバイト数。</span><span class="sxs-lookup"><span data-stu-id="9135c-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9135c-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="9135c-112">Return Value</span></span>  
 <span data-ttu-id="9135c-113">`true`正常に完了した場合は。それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="9135c-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9135c-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="9135c-114">Remarks</span></span>  
 <span data-ttu-id="9135c-115">関数が正常に完了しない場合は、[StrongNameErrorInfo](strongnameerrorinfo-function.md) 関数を呼び出して、最後に生成されたエラーを取得します。`StrongNameSignatureSize`</span><span class="sxs-lookup"><span data-stu-id="9135c-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9135c-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="9135c-116">Requirements</span></span>  
 <span data-ttu-id="9135c-117">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9135c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9135c-118">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="9135c-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9135c-119">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="9135c-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9135c-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9135c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9135c-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="9135c-121">See also</span></span>

- [<span data-ttu-id="9135c-122">StrongNameSignatureSize メソッド</span><span class="sxs-lookup"><span data-stu-id="9135c-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="9135c-123">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9135c-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
