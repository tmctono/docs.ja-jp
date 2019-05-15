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
ms.openlocfilehash: 7121ace6777e7cf947fcc6ff30b1ea314851feff
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636715"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="a153b-102">StrongNameKeyInstall 関数</span><span class="sxs-lookup"><span data-stu-id="a153b-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="a153b-103">公開/秘密キーの組がコンテナーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="a153b-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="a153b-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="a153b-104">This function has been deprecated.</span></span> <span data-ttu-id="a153b-105">使用して、 [iclrstrongname::strongnamekeyinstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="a153b-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="a153b-106">構文</span><span class="sxs-lookup"><span data-stu-id="a153b-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="a153b-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a153b-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="a153b-108">[in]キー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="a153b-108">[in] The name of the key container.</span></span> <span data-ttu-id="a153b-109">`wszKeyContainer` 空でない文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a153b-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="a153b-110">[in]バイナリ キーのペアです。</span><span class="sxs-lookup"><span data-stu-id="a153b-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="a153b-111">[in]サイズ (バイト単位) の`pbKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="a153b-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="a153b-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="a153b-112">Return Value</span></span>

<span data-ttu-id="a153b-113">`true` 正常に終了します。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="a153b-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a153b-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="a153b-114">Remarks</span></span>

<span data-ttu-id="a153b-115">使用して、 [StrongNameKeyDelete](strongnamekeydelete-function.md)キー コンテナーを削除する関数。</span><span class="sxs-lookup"><span data-stu-id="a153b-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="a153b-116">場合、`StrongNameKeyInstall`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="a153b-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="a153b-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="a153b-117">Requirements</span></span>

<span data-ttu-id="a153b-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a153b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="a153b-119">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a153b-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="a153b-120">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="a153b-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="a153b-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a153b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a153b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="a153b-122">See also</span></span>

- [<span data-ttu-id="a153b-123">StrongNameKeyInstall メソッド</span><span class="sxs-lookup"><span data-stu-id="a153b-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="a153b-124">StrongNameKeyDelete メソッド</span><span class="sxs-lookup"><span data-stu-id="a153b-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="a153b-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a153b-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
