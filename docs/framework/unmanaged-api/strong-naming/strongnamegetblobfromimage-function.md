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
ms.openlocfilehash: 86b99b29a85f498a6bfa0363a446bf589876bff9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799091"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="b3feb-102">StrongNameGetBlobFromImage 関数</span><span class="sxs-lookup"><span data-stu-id="b3feb-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="b3feb-103">指定したメモリ アドレスにあるアセンブリ イメージのバイナリ表現が取得されます。</span><span class="sxs-lookup"><span data-stu-id="b3feb-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="b3feb-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="b3feb-104">This function has been deprecated.</span></span> <span data-ttu-id="b3feb-105">代わりに[ICLRStrongName:: StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="b3feb-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3feb-106">構文</span><span class="sxs-lookup"><span data-stu-id="b3feb-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3feb-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3feb-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="b3feb-108">からマップされたアセンブリマニフェストのメモリアドレス。</span><span class="sxs-lookup"><span data-stu-id="b3feb-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="b3feb-109">からにある`pbBase`イメージのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="b3feb-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="b3feb-110">からイメージのバイナリ表現を格納するバッファー。</span><span class="sxs-lookup"><span data-stu-id="b3feb-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="b3feb-111">[入力、出力]要求された最大サイズ (バイト`pbBlob`単位)。</span><span class="sxs-lookup"><span data-stu-id="b3feb-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="b3feb-112">戻り時に、の実際の`pbBlob`サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="b3feb-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3feb-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="b3feb-113">Return Value</span></span>  
 <span data-ttu-id="b3feb-114">`true`正常に完了した場合は。それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="b3feb-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3feb-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="b3feb-115">Remarks</span></span>  
 <span data-ttu-id="b3feb-116">関数が正常に完了しない場合は、[StrongNameErrorInfo](strongnameerrorinfo-function.md) 関数を呼び出して、最後に生成されたエラーを取得します。`StrongNameGetBlobFromImage`</span><span class="sxs-lookup"><span data-stu-id="b3feb-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3feb-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="b3feb-117">Requirements</span></span>  
 <span data-ttu-id="b3feb-118">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3feb-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3feb-119">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="b3feb-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b3feb-120">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="b3feb-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3feb-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3feb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3feb-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3feb-122">See also</span></span>

- [<span data-ttu-id="b3feb-123">StrongNameGetBlobFromImage メソッド</span><span class="sxs-lookup"><span data-stu-id="b3feb-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="b3feb-124">StrongNameGetBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="b3feb-124">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="b3feb-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b3feb-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
