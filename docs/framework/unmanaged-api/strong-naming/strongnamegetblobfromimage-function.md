---
title: StrongNameGetBlobFromImage 関数
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
ms.openlocfilehash: 41226cd909900bd2da7bdcf9b9a49567d3042b01
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73094888"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="aed90-102">StrongNameGetBlobFromImage 関数</span><span class="sxs-lookup"><span data-stu-id="aed90-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="aed90-103">指定したメモリ アドレスにあるアセンブリ イメージのバイナリ表現が取得されます。</span><span class="sxs-lookup"><span data-stu-id="aed90-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="aed90-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="aed90-104">This function has been deprecated.</span></span> <span data-ttu-id="aed90-105">代わりに[ICLRStrongName:: StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="aed90-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aed90-106">構文</span><span class="sxs-lookup"><span data-stu-id="aed90-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aed90-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aed90-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="aed90-108">からマップされたアセンブリマニフェストのメモリアドレス。</span><span class="sxs-lookup"><span data-stu-id="aed90-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="aed90-109">から`pbBase`にあるイメージのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="aed90-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="aed90-110">からイメージのバイナリ表現を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="aed90-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="aed90-111">[入力、出力]`pbBlob`の要求された最大サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="aed90-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="aed90-112">返されたときに、`pbBlob`の実際のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="aed90-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aed90-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="aed90-113">Return Value</span></span>  
 <span data-ttu-id="aed90-114">正常に完了した場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="aed90-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aed90-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="aed90-115">Remarks</span></span>  
 <span data-ttu-id="aed90-116">`StrongNameGetBlobFromImage` 関数が正常に完了しない場合は、 [StrongNameErrorInfo](strongnameerrorinfo-function.md)関数を呼び出して、最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="aed90-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aed90-117">［要件］</span><span class="sxs-lookup"><span data-stu-id="aed90-117">Requirements</span></span>  
 <span data-ttu-id="aed90-118">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aed90-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aed90-119">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="aed90-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="aed90-120">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="aed90-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aed90-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aed90-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aed90-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="aed90-122">See also</span></span>

- [<span data-ttu-id="aed90-123">StrongNameGetBlobFromImage メソッド</span><span class="sxs-lookup"><span data-stu-id="aed90-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="aed90-124">StrongNameGetBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="aed90-124">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="aed90-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="aed90-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
