---
title: IAssemblyCacheItem::CreateStream メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
ms.openlocfilehash: 0660621f465f2ba3610e06bd1df38baa1bc5c907
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134469"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="bd3de-102">IAssemblyCacheItem::CreateStream メソッド</span><span class="sxs-lookup"><span data-stu-id="bd3de-102">IAssemblyCacheItem::CreateStream Method</span></span>

<span data-ttu-id="bd3de-103">指定された名前と形式を使用してストリームを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd3de-103">Creates a stream with the specified name and format.</span></span>

## <a name="syntax"></a><span data-ttu-id="bd3de-104">構文</span><span class="sxs-lookup"><span data-stu-id="bd3de-104">Syntax</span></span>

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a><span data-ttu-id="bd3de-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bd3de-105">Parameters</span></span>

`dwFlags`\
<span data-ttu-id="bd3de-106">からFusion に定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="bd3de-106">[in] Flags defined in Fusion.idl.</span></span>

`pszStreamName`\
<span data-ttu-id="bd3de-107">から作成されるストリームの名前。</span><span class="sxs-lookup"><span data-stu-id="bd3de-107">[in] The name of the stream to be created.</span></span>

`dwFormat`\
<span data-ttu-id="bd3de-108">からストリーム配信されるファイルの形式。</span><span class="sxs-lookup"><span data-stu-id="bd3de-108">[in] The format of the file to be streamed.</span></span>

`dwFormatFlags`\
<span data-ttu-id="bd3de-109">からFusion に定義されている形式固有のフラグ。</span><span class="sxs-lookup"><span data-stu-id="bd3de-109">[in] Format-specific flags defined in Fusion.idl.</span></span>

`ppIStream`\
<span data-ttu-id="bd3de-110">入出力返された[IStream](/windows/desktop/api/objidl/nn-objidl-istream)インスタンスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bd3de-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>

`puliMaxSize`\
<span data-ttu-id="bd3de-111">[in、optional]`ppIStream`によって参照されるストリームの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="bd3de-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>

## <a name="requirements"></a><span data-ttu-id="bd3de-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="bd3de-112">Requirements</span></span>

<span data-ttu-id="bd3de-113">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd3de-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="bd3de-114">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="bd3de-114">**Header:** Fusion.h</span></span>

<span data-ttu-id="bd3de-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd3de-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bd3de-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd3de-116">See also</span></span>

- [<span data-ttu-id="bd3de-117">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bd3de-117">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
