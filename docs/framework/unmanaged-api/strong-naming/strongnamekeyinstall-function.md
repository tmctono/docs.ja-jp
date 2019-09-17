---
title: StrongNameKeyInstall 関数
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 353898b72f41acd0c49a43ff05e54f61b99444c4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799000"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="ff902-102">StrongNameKeyInstall 関数</span><span class="sxs-lookup"><span data-stu-id="ff902-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="ff902-103">公開/秘密キーの組がコンテナーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ff902-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="ff902-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="ff902-104">This function has been deprecated.</span></span> <span data-ttu-id="ff902-105">代わりに[ICLRStrongName:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="ff902-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="ff902-106">構文</span><span class="sxs-lookup"><span data-stu-id="ff902-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="ff902-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ff902-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="ff902-108">からキーコンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="ff902-108">[in] The name of the key container.</span></span> <span data-ttu-id="ff902-109">`wszKeyContainer`は空でない文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff902-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="ff902-110">からバイナリキーペア。</span><span class="sxs-lookup"><span data-stu-id="ff902-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="ff902-111">からの`pbKeyBlob`サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="ff902-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="ff902-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="ff902-112">Return Value</span></span>

<span data-ttu-id="ff902-113">`true`正常に完了した場合は。それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="ff902-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff902-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="ff902-114">Remarks</span></span>

<span data-ttu-id="ff902-115">キーコンテナーを削除するには、 [StrongNameKeyDelete](strongnamekeydelete-function.md)関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="ff902-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="ff902-116">関数が正常に完了しない場合は、[StrongNameErrorInfo](strongnameerrorinfo-function.md) 関数を呼び出して、最後に生成されたエラーを取得します。`StrongNameKeyInstall`</span><span class="sxs-lookup"><span data-stu-id="ff902-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="ff902-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="ff902-117">Requirements</span></span>

<span data-ttu-id="ff902-118">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff902-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ff902-119">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="ff902-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="ff902-120">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ff902-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="ff902-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff902-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ff902-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff902-122">See also</span></span>

- [<span data-ttu-id="ff902-123">StrongNameKeyInstall メソッド</span><span class="sxs-lookup"><span data-stu-id="ff902-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="ff902-124">StrongNameKeyDelete メソッド</span><span class="sxs-lookup"><span data-stu-id="ff902-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="ff902-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff902-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
