---
title: StrongNameKeyDelete 関数
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
ms.openlocfilehash: d37f990241ae704abef55d863da0f40a31284837
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141587"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="126b0-102">StrongNameKeyDelete 関数</span><span class="sxs-lookup"><span data-stu-id="126b0-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="126b0-103">指定したキー コンテナーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="126b0-103">Deletes the specified key container.</span></span>

<span data-ttu-id="126b0-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="126b0-104">This function has been deprecated.</span></span> <span data-ttu-id="126b0-105">代わりに[ICLRStrongName:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="126b0-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="126b0-106">構文</span><span class="sxs-lookup"><span data-stu-id="126b0-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="126b0-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="126b0-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="126b0-108">から削除するキーコンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="126b0-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="126b0-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="126b0-109">Return Value</span></span>

<span data-ttu-id="126b0-110">正常に完了した場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="126b0-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="126b0-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="126b0-111">Remarks</span></span>

<span data-ttu-id="126b0-112">公開/秘密キーのペアをコンテナーにインポートするには、 [StrongNameKeyInstall](strongnamekeyinstall-function.md)関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="126b0-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="126b0-113">`StrongNameKeyDelete` 関数が正常に完了しない場合は、 [StrongNameErrorInfo](strongnameerrorinfo-function.md)関数を呼び出して、最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="126b0-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="126b0-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="126b0-114">Requirements</span></span>

<span data-ttu-id="126b0-115">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="126b0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="126b0-116">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="126b0-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="126b0-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="126b0-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="126b0-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="126b0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="126b0-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="126b0-119">See also</span></span>

- [<span data-ttu-id="126b0-120">StrongNameKeyDelete メソッド</span><span class="sxs-lookup"><span data-stu-id="126b0-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="126b0-121">StrongNameKeyInstall メソッド</span><span class="sxs-lookup"><span data-stu-id="126b0-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="126b0-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="126b0-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
