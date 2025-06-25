<details open>
<summary>Elm Code Block</summary>

```elm
module Main exposing (..)

{-| Here's a block of "documentation" code
That you can use to generate docs in Elm I think -}

import Browser as B exposing (..)

type Msg
  = ToMessage Int

onSlide : (Int -> msg) -> Attribute msg
onSlide toMsg =
  let
    detailUserSlidTo : Decode Int  -- A Json Decoder
    detailUserSlidTo =
      at [ "detail", "userSlidTo" ] int
    msgDecoder : Decoder msg  -- Maps to a Message
    msgDecoder =
      Json.Decode.map ToMsg detailUserSlidTo
  in
  on "slide" msgDecoder  -- Html.Event
at [ "detail", "userSlidTo" ] int  -- <internals> : Decoder Int
    |> Json.Decode.map ToMsg  -- <function> : Decoder Int -> Decoder Msg
    |> on "slide"  -- <function> : Decoder msg -> Html.Attribute ms


-- view --
view : Model -> Html Msg
view model =
  div [ id "choose-size" ]
    -- How can we clean up this section of the code?
    [ viewSizeChooser Small, viewSizeChooser Medium, viewSizeChooser Large ]

viewSizeChooser : ThumbnailSize -> Html Msg  -- #3
viewSizeChooser size =
  span [] [
    label []
    [ input [
        type_ "radio", name "size", onClick (ClickedSize size)  -- Handled by `Msg`
      ] []
    , text (sizeToString size)
    ]
  ]

-- case --
sizeToString : ThumbnailSize -> String
sizeToString size =
  case size of
      Small -> "small"
      Medium -> "med"
      Large -> "large"


-- model --
type ThumbnailSize
  = Small
  | Medium
  | Large
```

</details>
