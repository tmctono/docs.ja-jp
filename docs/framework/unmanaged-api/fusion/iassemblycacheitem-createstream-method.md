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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a98273307003485202d8c12d5c27fda04ff5a0ae
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65629874"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="41874-102">IAssemblyCacheItem::CreateStream メソッド</span><span class="sxs-lookup"><span data-stu-id="41874-102">IAssemblyCacheItem::CreateStream Method</span></span>

<span data-ttu-id="41874-103">指定した名前と形式を使用するストリームを作成します。</span><span class="sxs-lookup"><span data-stu-id="41874-103">Creates a stream with the specified name and format.</span></span>

## <a name="syntax"></a><span data-ttu-id="41874-104">構文</span><span class="sxs-lookup"><span data-stu-id="41874-104">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="41874-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41874-105">Parameters</span></span>

`dwFlags`\
<span data-ttu-id="41874-106">[in]ものがありますで定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="41874-106">[in] Flags defined in Fusion.idl.</span></span>

`pszStreamName`\
<span data-ttu-id="41874-107">[in]作成されるストリームの名前。</span><span class="sxs-lookup"><span data-stu-id="41874-107">[in] The name of the stream to be created.</span></span>

`dwFormat`\
<span data-ttu-id="41874-108">[in]ストリーミングされるように、ファイルの形式です。</span><span class="sxs-lookup"><span data-stu-id="41874-108">[in] The format of the file to be streamed.</span></span>

`dwFormatFlags`\
<span data-ttu-id="41874-109">[in]形式固有のものがありますで定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="41874-109">[in] Format-specific flags defined in Fusion.idl.</span></span>

`ppIStream`\
<span data-ttu-id="41874-110">[out]返されるのアドレスへのポインター [IStream](/windows/desktop/api/objidl/nn-objidl-istream)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="41874-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>

`puliMaxSize`\
<span data-ttu-id="41874-111">[in、省略可能]によって参照されるストリームの最大サイズ`ppIStream`します。</span><span class="sxs-lookup"><span data-stu-id="41874-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>

## <a name="requirements"></a><span data-ttu-id="41874-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="41874-112">Requirements</span></span>

<span data-ttu-id="41874-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41874-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="41874-114">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="41874-114">**Header:** Fusion.h</span></span>

<span data-ttu-id="41874-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41874-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="41874-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="41874-116">See also</span></span>

- [<span data-ttu-id="41874-117">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="41874-117">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
