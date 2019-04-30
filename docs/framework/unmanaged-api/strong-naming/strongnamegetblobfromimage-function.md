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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b136e1fa480e53bcacfd9ea832d1dc4d1bd69f74
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000299"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="e34a3-102">StrongNameGetBlobFromImage 関数</span><span class="sxs-lookup"><span data-stu-id="e34a3-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="e34a3-103">指定したメモリ アドレスにあるアセンブリ イメージのバイナリ表現が取得されます。</span><span class="sxs-lookup"><span data-stu-id="e34a3-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="e34a3-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="e34a3-104">This function has been deprecated.</span></span> <span data-ttu-id="e34a3-105">使用して、 [iclrstrongname::strongnamegetblobfromimage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="e34a3-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e34a3-106">構文</span><span class="sxs-lookup"><span data-stu-id="e34a3-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e34a3-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e34a3-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="e34a3-108">[in]マップされているアセンブリ マニフェストのメモリ アドレス。</span><span class="sxs-lookup"><span data-stu-id="e34a3-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="e34a3-109">[in]サイズをバイト単位でイメージの`pbBase`します。</span><span class="sxs-lookup"><span data-stu-id="e34a3-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="e34a3-110">[in]画像のバイナリ表現を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="e34a3-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="e34a3-111">[入力、出力]最大サイズ (バイト単位) を要求された`pbBlob`します。</span><span class="sxs-lookup"><span data-stu-id="e34a3-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="e34a3-112">関数が戻るとき、実際のサイズをバイト単位の`pbBlob`します。</span><span class="sxs-lookup"><span data-stu-id="e34a3-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e34a3-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="e34a3-113">Return Value</span></span>  
 <span data-ttu-id="e34a3-114">`true` 正常に終了します。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="e34a3-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e34a3-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="e34a3-115">Remarks</span></span>  
 <span data-ttu-id="e34a3-116">場合、`StrongNameGetBlobFromImage`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="e34a3-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e34a3-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="e34a3-117">Requirements</span></span>  
 <span data-ttu-id="e34a3-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e34a3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e34a3-119">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="e34a3-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e34a3-120">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e34a3-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e34a3-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e34a3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e34a3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e34a3-122">See also</span></span>

- [<span data-ttu-id="e34a3-123">StrongNameGetBlobFromImage メソッド</span><span class="sxs-lookup"><span data-stu-id="e34a3-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="e34a3-124">StrongNameGetBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="e34a3-124">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="e34a3-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e34a3-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
