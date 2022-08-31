FROM alpine:3.16

ENV FONT_DIR /usr/share/fonts/ttf

RUN mkdir -p $FONT_DIR
COPY tmp_assets/Montserrat/*.ttf $FONT_DIR
COPY tmp_assets/DharmaGothicExtended/*.otf $FONT_DIR
RUN apk add --no-cache inkscape \
  fontconfig \
  && fc-cache -f

WORKDIR /data
ENTRYPOINT ["inkscape", "--export-area-drawing", "--batch-process", "--export-type=pdf"]
